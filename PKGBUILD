# Maintainer: Mykola Matvyeyev <mnasoft@gmail.com>
pkgname=tar-xz-slicer
pkgver=0.2
pkgrel=1
pkgdesc="CLI-утилита для упаковки каталогов в .tar.xz с нарезкой на слайсы и распаковкой без временных файлов"
arch=('any')
url="https://github.com/mnasoft/tar-xz-slicer"
license=('MIT')
depends=('bash' 'xz' 'coreutils' 'tar')
makedepends=()
#source=(
#  "${pkgname}"         # основной скрипт
#  #  "man/${pkgname}.1"   # man-страница
#  "man/tar-xz-slicer.1"
#)
source=(
  "${pkgname}"
  "${pkgname}.1"
)
noextract=("${pkgname}.1")

sha256sums=('SKIP' 'SKIP')  # 'SKIP' для начала можно пропустить; позже можно зафиксировать

package() {
  install -Dm755 "${srcdir}/${pkgname}" "${pkgdir}/usr/bin/${pkgname}"

  # Man-page
  install -d "${pkgdir}/usr/share/man/man1"
  gzip -c "${srcdir}/${pkgname}.1" > "${pkgdir}/usr/share/man/man1/${pkgname}.1.gz"

  # (опционально) можно добавить лицензию
  # install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
