# SPDX-License-Identifier: AGPL-3.0

#    -----------------------------------------------------
#    Copyright © 2024, 2025, 2026  Pellegrino Prevete
#
#    All rights reserved
#    -----------------------------------------------------
#
#    This program is free software: you can redistribute
#    it and/or modify it under the terms of the
#    GNU Affero General Public License as published by
#    the Free Software Foundation, either version 3 of
#    the License, or (at your option) any later version.
#
#    This program is distributed in the hope that it
#    will be useful, but WITHOUT ANY WARRANTY;
#    without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
#    See the GNU Affero General Public License for
#    more details.
#
#    You should have received a copy of the
#    GNU Affero General Public License
#    along with this program.
#    If not, see <https://www.gnu.org/licenses/>.

# Maintainers:
#   Truocolo
#     <truocolo@aol.com>
#     <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
#   Pellegrino Prevete (dvorak)
#     <pellegrinoprevete@gmail.com>
#     <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>
#   Jaroslav Lichtblau
#     <svetlemodry@archlinux.org>
# Contributors:
#   Thorsten Töpper
#     <atsutane-tu@freethoughts.de>
#   Francois Boulogne
#     <fboulogne at april dot org>
#   Andre Klitzing
#     <aklitzing () online () de>
#   Allan McRae
#     <mcrae_allan@hotmail.com>
#   Mikko Seppälä (Neverth)
#     <t-r-a-y@mbnet.fi>

if [[ ! -v "_ns" ]]; then
  _ns="mquinson"
  _ns="themartiancompany"
fi
pkgver=0.74
_pkg=po4a
_pkgbase="${_pkg}"
pkgname=(
  "${_pkg}"
)
pkgrel=1
_pkgdesc=(
  "Tools for helping translation of documentation"
)
pkgdesc="${pkgdesc[*]}"
arch=(
  'any'
)
url="https://${_pkg}.org"
license=(
  'GPL'
)
depends=(
  'perl'
  'gettext'
  'perl-yaml-tiny'
  'perl-unicode-linebreak'
)
makedepends=(
  'perl-text-wrapi18n'
  'perl-locale-gettext'
  'perl-term-readkey'
  'perl-sgmls'
  'perl-module-build'
  'perl-pod-parser'
  'docbook-xsl'
)
options=(
  '!emptydirs'
)
_tarname="${_pkg}-${pkgver}"
_http="https://github.com"
_url="${_http}/${_ns}/${_pkg}"
source=(
  "${_tarname}.tar.gz::${_url}/archive/v${pkgver}.tar.gz"
)
sha256sums=(
  '6e390eb7707501a86f2e648d78fddb0d211d1e8699aa1ee201176e9f966a798b'
)

build() {
  cd \
    "${_tarname}"
  # The script expects a UTF-8 locale
  LC_ALL="en_US.UTF-8" \
  perl \
    "Build"
}

package() {
  cd \
    "${_tarname}"
  perl \
    "Build" \
    destdir="${pkgdir}" \
    install
}
