#!/bin/bash

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <archiv8@artisteducator.com>
# Contributor: Ross Clark <archiv8@artisteducator.com>

pkgname=openh264
pkgver=2.1.1
pkgrel=1
pkgdesc='OpenH264 is a codec library which supports H.264 encoding and decoding'
license=('BSD')
arch=('x86_64' 'i686' 'aarch64')
url="http://www.openh264.org/"
depends=('gcc-libs')
makedepends=('nasm')
source=("https://github.com/cisco/openh264/archive/v${pkgver}.tar.gz")
sha256sums=('af173e90fce65f80722fa894e1af0d6b07572292e76de7b65273df4c0a8be678')

build() {
  cd "openh264-$pkgver"
  make
}

package() {
  cd "openh264-$pkgver"
  make DESTDIR="$pkgdir" PREFIX="/usr" install
  install -Dm755 h264dec "$pkgdir"/usr/bin/h264dec
  install -Dm755 h264enc "$pkgdir"/usr/bin/h264enc
  install -Dm644 LICENSE "$pkgdir"/usr/share/licenses/$pkgname/LICENSE
}

# vim:set ts=2 sw=2 et:
