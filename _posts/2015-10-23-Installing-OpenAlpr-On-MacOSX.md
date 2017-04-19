---
layout: post
title: Installing OpenAlpr on MacOSX
tags: [OpenAlpr, MacOSx]
categories: ['Computer-Vision']
---

[OpenAlpr](https://github.com/openalpr/openalpr) is a great open source Automatic Licence Plate Recognition Library. However I had few struggles in the installation on MacOSX and used Ubuntu on VM instead. The main problem was with the update on the Tesseract from 3.03 to 3.04. Few days ago, the developers trained the data set again for the updated Tesseract and I decided to have a go at the installation again. Here are my steps.

### Installing Dependencies with Homebrew
    brew install tesseract --devel
    brew install cmake
    brew tap homebrew/science
    brew install opencv
    brewinstall log4cplus

### Building the package
    git clone https://github.com/openalpr/openalpr.git
    cd openalpr/src
    mkdir build
    cd build

Up to here, everything is exactly same with their guide, however, every time I tried to continue, I was having an error and after searching their Q&A database, I found that I needed to add the line "link_directories(/usr/local/lib/)" to the file "CMakeLists.txt" and then continue with the following.

    cmake -DCMAKE_INSTALL_PREFIX:PATH=/usr -DCMAKE_INSTALL_SYSCONFDIR:PATH=/etc ..
    make
    sudo make install

Then if everything went fine, it should be installed and ready to go. You can test it by downloading a license plate image from google and use

    alpr -c COUNTRY_CODE IMAGE_NAME.jpg

Country code can be "us" for United States and "eu" Europe plates.
