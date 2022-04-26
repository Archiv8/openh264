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
pkgver=2.2.0
pkgrel=1
pkgdesc="OpenH264 is a codec library which supports H.264 encoding and decoding"
license=("BSD")
arch=("x86_64" "i686" "aarch64")
url="http://www.openh264.org/"
depends=(
  "gcc-libs"
  )
makedepends=(
  "nasm"
  )
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/cisco/${e4e5c8ba48e64ba6ce61e8b6e2b76b2d870c74c270147649082feabb40f25905pkgname}/archive/v${pkgver}.tar.gz")
sha512sums=(
  "637e2bfa45ad586c10fc8990cad4d824ada07e277fd965c3a6cdd19bc7836b2d7082574037a3ff2ee631207dd8cb0ec4f68abafdc19646b433de561c47ce8d38"
  )

build() {
  cd "${pkgname}-${pkgver}"
  make
}

package() {
  cd "${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" PREFIX="/usr" install
  install -Dm755 h264dec "${pkgdir}"/usr/bin/h264dec
  install -Dm755 h264enc "${pkgdir}"/usr/bin/h264enc
  install -Dm644 LICENSE "${pkgdir}"/usr/share/licenses/$pkgname/LICENSE
}
