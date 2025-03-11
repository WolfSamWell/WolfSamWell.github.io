---
layout: post
title: '移动端开发'
subtitle: '知识记录'
date: 2025-03-10
categories: 技术文章
cover: 'http://on2171g4d.bkt.clouddn.com/jekyll-theme-h2o-postcover.jpg'
tags:  iOS SDK xcframework
---



### 一 iOS 的静态库的合并

 记录一个脚本合并SDK项目下的模拟器和真机为通用的xcFramework



```sh
#!/bin/sh
# 放在与 .xcodeproj 文件同级目录下，生成结果在 build 目录下

# 需要编译的 scheme
scheme="Sdk项目名称"

if [ -z "$scheme" ] || [ "$scheme" = "" ]; then
     echo "请填入 scheme 名称"
fi

echo "scheme: $scheme"
cd "$(dirname "$0")" || exit 0

xcodebuild archive \
    -scheme "$scheme" \
    -sdk iphoneos \
    -archivePath "archives/ios_devices.xcarchive" \
    BUILD_LIBRARY_FOR_DISTRIBUTION=YES \
    SKIP_INSTALL=NO

xcodebuild archive \
    -scheme "$scheme" \
    -sdk iphonesimulator \
    -archivePath "archives/ios_simulators.xcarchive" \
    BUILD_LIBRARY_FOR_DISTRIBUTION=YES \
    SKIP_INSTALL=NO

# 优先从 archive 文件夹下读取
product_list=$(ls archives/ios_devices.xcarchive/Products/Library/Frameworks)
for file_name in $product_list
do
    full_product_name=$file_name
    break
done

# 读取不到就从 showBuildSettings 读取
if [ -z "$full_product_name" ] || [ "$full_product_name" = "" ]; then
    name_dict=$(xcodebuild -showBuildSettings | grep FULL_PRODUCT_NAME)
    full_product_name=${name_dict#*= }
fi

product_name=${full_product_name%.*}

xcodebuild -create-xcframework \
    -framework archives/ios_devices.xcarchive/Products/Library/Frameworks/"$full_product_name" \
    -framework archives/ios_simulators.xcarchive/Products/Library/Frameworks/"$full_product_name" \
    -output build/"$product_name".xcframework

```



 然后执行该脚本：

```sh
➜  ~ sh 脚本名.sh
```



