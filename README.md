go-sqlcipher
==========

SQLCipher driver conforming to the built-in database/sql interface and using the latest sqlite3 code.

which is
`3.8.8.3 2015-02-25 13:29:11 9d6c1880fb75660bbabd693175579529785f8a6b`

Working with sqlcipher version which is
`3.8.6 2014-08-15 11:46:33 9491ba7d738528f168657adb43a198238abde19e`

It's wrapper with
 * [go-sqlite3](https://github.com/mattn/go-sqlite3) sqlite3 driver for go that using database/sql.
 * [SQLCipher](https://github.com/sqlcipher/sqlcipher) SQLCipher is an SQLite extension that provides 256 bit AES encryption of database files.
 * Using [openssl](https://github.com/openssl/openssl) as the 256 bit AES encryption.

*Have't build test in a windows machine or linux machine*
**Working in my macbook-air**
```
Configured with: --prefix=/Applications/Xcode.app/Contents/Developer/usr --with-gxx-include-dir=/usr/include/c++/4.2.1
Apple LLVM version 6.0 (clang-600.0.56) (based on LLVM 3.5svn)
Target: x86_64-apple-darwin14.3.0
Thread model: posix

OpenSSL 0.9.8zd 8 Jan 2015
built on: Mar  9 2015
platform: darwin64-x86_64-llvm
options:  bn(64,64) md2(int) rc4(ptr,char) des(idx,cisc,16,int) blowfish(idx)
compiler: -arch x86_64 -fmessage-length=0 -pipe -Wno-trigraphs -fpascal-strings -fasm-blocks -O3 -D_REENTRANT -DDSO_DLFCN -DHAVE_DLFCN_H -DL_ENDIAN -DMD32_REG_T=int -DOPENSSL_NO_IDEA -DOPENSSL_PIC -DOPENSSL_THREADS -DZLIB -mmacosx-version-min=10.6
OPENSSLDIR: "/System/Library/OpenSSL"

```

Installation
------------

This package can be installed with the go get command:

    go get github.com/xeodou/go-sqlcipher

Documentation
-------------

API documentation can be found here: http://godoc.org/github.com/xeodou/go-sqlcipher

Examples can be found under the `./_example` directory

FAQ
---

The golang code is copy from [go-sqlite3](https://github.com/mattn/go-sqlite3)
If you have some issue, you can maybe you can find from https://github.com/mattn/go-sqlite3/issues

Here is some help from go-sqlite3 project.

* Can't build go-sqlite3 on windows 64bit.

    > Probably, you are using go 1.0, go1.0 has a problem when it comes to compiling/linking on windows 64bit.
    > See: https://github.com/mattn/go-sqlite3/issues/27

* Getting insert error while query is opened.

    > You can pass some arguments into the connection string, for example, a URI.
    > See: https://github.com/mattn/go-sqlite3/issues/39

* Do you want cross compiling? mingw on Linux or Mac?

    > See: https://github.com/mattn/go-sqlite3/issues/106
    > See also: http://www.limitlessfx.com/cross-compile-golang-app-for-windows-from-linux.html

* Want to get time.Time with current locale

    Use `loc=auto` in SQLite3 filename schema like `file:foo.db?loc=auto`.

* Print some waring messages like `warning: 'RAND_add' is deprecated: first deprecated in OS X 10.7`

    You can ignore these messages.

License
-------

MIT:

sqlite3-binding.c, sqlite3-binding.h, sqlite3ext.h

The -binding suffix was added to avoid build failures under gccgo.

In this repository, those files are amalgamation code that copied from SQLCipher. The license of those codes are depend on the license of SQLCipher.

Author
------

[xeodou](https://xeodou.me)
