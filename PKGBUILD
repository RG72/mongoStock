# $Id: PKGBUILD 138045 2015-08-07 07:12:16Z fyan $
# Maintainer: Felix Yan <felixonmars@archlinux.org>
# Contributor: Sven-Hendrik Haase <sh@lutzhaase.com>
# Contributor: Thomas Dziedzic < gostrc at gmail >
# Contributor: Mathias Stearn <mathias@10gen.com>
# Contributor: Alec Thomas

pkgname=mongodbStock
pkgver=3.0.6
pkgrel=1
pkgdesc='A high-performance, open source, schema-free document-oriented database'
arch=('x86_64')
url='http://www.mongodb.org'
license=('AGPL3')
conflicts=('mongodb')
backup=('etc/mongodb.conf')
install=mongodb.install
source=("https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-${pkgver}.tgz"
        'mongodb.conf' 'mongodb.service')

sha512sums=('5b29975d4d9fa2495eb3a4f02cd9fb32bd9e17f3294ee92497eec016466182f28afb429153d9f9287039b4160da76ee69f85492bfab144c4ed108e0ba0dc7874'
            '05dead727d3ea5fe8af1a3c3888693f6b3e2b8cb7f197a5d793352e10d2c524e96c9a5c55ad2e88c1114643a9612ec0b26a2574b48a5260a9b51ec8941461f1c'
            '177251404b2e818ae2b546fe8b13cb76e348c99e85c7bef22a04b0f07b600fd515a309ede50214f4198594388a6d2b31f46e945b9dae84aabb4dfa13b1123bb9')

package() {
  cd "$srcdir/mongodb-linux-x86_64-${pkgver}/bin"
  for f in *; do
    #echo $f
    install -Dm755 "$srcdir/mongodb-linux-x86_64-${pkgver}/bin/$f" "$pkgdir/usr/bin/$f"
  done
  
  install -Dm644 "$srcdir/mongodb.conf" "$pkgdir/etc/mongodb.conf"
  install -Dm644 "$srcdir/mongodb.service" "$pkgdir/usr/lib/systemd/system/mongodb.service"
  install -dm700 "$pkgdir/var/lib/mongodb"
  install -dm755 "$pkgdir/var/log/mongodb"
}
