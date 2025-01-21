# SPDX-License-Identifier: AGPL-3.0

#    ----------------------------------------------------------------------
#    Copyright © 2025  Pellegrino Prevete
#
#    All rights reserved
#    ----------------------------------------------------------------------
#
#    This program is free software: you can redistribute it and/or modify
#    it under the terms of the GNU Affero General Public License as published by
#    the Free Software Foundation, either version 3 of the License, or
#    (at your option) any later version.
#
#    This program is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU Affero General Public License for more details.
#
#    You should have received a copy of the GNU Affero General Public License
#    along with this program.  If not, see <https://www.gnu.org/licenses/>.

# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>

_offline="false"
_git="false"
pkgname="ipfs-dlagent"
pkgver=0.1.1
pkgrel=1
_commit="4627bd5d582dfd769f9954ee88d1f1984f190d5b"
pkgdesc="makepkg download agent for IPFS URIs."
arch=(
  'any'
)
_http="https://github.com"
_ns="themartiancompany"
url="${_http}/${_ns}/${pkgname}"
depends=(
  "kubo"
  "systemd"
)
license=(
  "AGPL3"
)
if [[ "${_git}" == "false" ]]; then
  _src="${pkgname}-${pkgver}.tar.gz::${url}/archive/refs/tags/${pkgver}.tar.gz"
  _sum='cb29d08ac74849ad5ea7343f061b9d89196839d9099f2832d4e25a1604e4f294'
elif [[ "${_git}" == "true" ]]; then
  _src="${pkgname}-${pkgver}::git+${url}#_commit=${_commit}"
  _sum='3be1df805d609534963e9d1e7d2ce1a3922a4d02a1dd41c2d364eeff86769802'
fi
if [[ "${_offline}" == "true" ]]; then
  _url="file://${HOME}/${pkgname}"
fi
source=(
  "${_src}"
)
sha256sums=(
  "${_sum}"
)

package() {
  cd \
    "${pkgname}-${pkgver}"
  make \
    PREFIX="/usr" \
    DESTDIR="${pkgdir}" \
    install
}
