# Maintainer: Pratyush <codelab@pratyush.dev>
pkgname=asfp
pkgver=2023.1.1.19
pkgrel=1
pkgdesc="Get the official Integrated Development Environment (IDE) for Android platform development."
arch=('x86_64')
url="https://developer.android.com/studio/platform"
license=('APACHE')
depends=('alsa-lib' 'freetype2' 'libxrender' 'libxtst' 'which')
optdepends=('gtk2: GTK+ look and feel'
            'libgl: emulator support'
            'ncurses5-compat-libs: native debugger support')
provides=('asfp')
options=('!emptydirs' '!strip')
source=("https://dl.google.com/android/asfp/asfp-${pkgver}-linux.deb"
		"asfp.desktop"
		"application-x-androidbp.xml")
sha512sums=('cfd9285eaaae7e186f5f898fc24112e2702b2e608efb050413136b662be6f702922d313285407e11cd7f689256b51551c09c97a382b98ac0defff790c813133f'
            '2f364e055eb38cd06f0e1ae7b4306d7a053c864e573ef7c131d79168d8ca81f46d534ee94009ed9cea8ce597736dea0721f16c62b6f5940ed7121012436b086f'
            '07ea2e5b1546d54f2114d6db8d6b0eabe6712c2bf46209c8ce3369bcf43163205a60d27b774be15fd3e09406359dacdf2f3dfc227009680683c1164557137571')

package() {
	bsdtar -xf data.tar.xz -C "$pkgdir/"
	install -d $pkgdir/opt/$pkgname
	install -dm 755 "${pkgdir}/usr/bin"
	install -Dm644 "/opt/android-studio-for-platform/bin/studio.png" $pkgdir/usr/share/pixmaps/$pkgname.png
	install -Dm644 "/opt/android-studio-for-platform/bin/studio.svg" $pkgdir/usr/share/pixmaps/$pkgname.svg

	install -Dm644 "${srcdir}/asfp.desktop" "${pkgdir}/usr/share/applications/${pkgname}.desktop"
 	install -Dm644 "${srcdir}/application-x-androidbp.xml" "${pkgdir}/usr/share/mine/androidbp.xml"

	ln -s "/opt/android-studio-for-platform/bin/studio.sh" "${pkgdir}/usr/bin/${pkgname}"
}
