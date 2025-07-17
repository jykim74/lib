# This package contains the LibXML2, LibXSLT, OpenSSL, and XMLSec binaries for Win64 (/MD runtime).

## LibXML2 (2.13.5)
```
cd win32
cscript configure.js iconv=no zlib=no cruntime=/MD prefix=c:\local\distro\libxml2
nmake
nmake install
```

## LibXSLT (1.1.42)
```
cd win32
cscript configure.js iconv=no zlib=no cruntime=/MD prefix=c:\local\distro\libxslt include=c:\local\distro\libxml2\include\libxml2 lib=c:\local\distro\libxml2\lib
nmake
nmake install
```

## OpenSSL (3.4.1)
```
C:\Strawberry\perl\bin\perl.exe Configure no-unit-test --prefix=c:\local\distro\openssl --release VC-WIN64A
nmake
nmake install_sw
```

## XMLSec (1.3.7)
```
cd win32
cscript configure.js pedantic=yes werror=yes with-dl=yes cruntime=/MD xslt=yes crypto=openssl,mscng unicode=yes prefix=C:\local\distro\xmlsec include=C:\local\distro\libxml2\include;C:\local\distro\libxml2\include\libxml2;C:\local\distro\libxslt\include;C:\local\distro\openssl\include; lib=C:\local\distro\libxml2\lib;C:\local\distro\libxslt\lib;C:\local\distro\openssl\lib
nmake
nmake install
```

## Archive
```
cd c:\local\distro
find . -name "*.pdb" -exec rm {} \;
zip -r xmlsec1-1.3.7-win64.zip libxml2 libxslt openssl xmlsec README.md
```
