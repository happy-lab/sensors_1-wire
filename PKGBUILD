#
# This is the PKGBUILD for One Wire Sensors MQTT Package
#

pkgname=sensors_1-wire
pkgver=1.1.0
pkgrel=1
pkgdesc="One Wire Sensors Publish Through MQTT"
arch=('i686' 'x86_64' 'arm' 'armv6h' 'armv7h')
url="http://happy-lab.llc/"
depends=('python' 'owfs')
provides=('sensors_1-wire')
license=('MIT')
source=("$pkgname" "$pkgname.service" "$pkgname.conf.example" "LICENSE"
        "owserver.service" "owserver.socket" "owfs.conf.example")
install=$pkgname.install
sha256sums=('7e4dc5e10b8ab837b3646677712deefc88992142713f14f9bdb0393f43d6f63d'
            'ee7df605e53c7755aecd017163e1c59f8fd16e06ba683f22869c4c669f0fd820'
            'fabeb2b9f6291920153ac1cdadd0bc5c72daa1fd6ab459e945fedb457d8e1f76'
            '86efd6ff86cea002a35a41101f8e56966f30889bfc8b5a210707de9ec8d4945f'
            '48ec5f5381adfb515bb17f985b2ddf341410e49e41933941b46b72b73353a575'
            '474d908e9f2df7a49837fc6f5214a17840a4ac7b044e57988f67e310b8f34962'
            'c5089bc858e3308732e9e9a0ddeb1ad36a77d628150c038ebcdf54027208218a')

package() {

  # Daemon
  install -Dm755 "$pkgname" "$pkgdir/usr/bin/$pkgname"

  # Daemon systemd service file
  install -Dm644 "$pkgname.service" "$pkgdir/usr/lib/systemd/system/$pkgname.service"

  # Daemon configuration file
  install -Dm644 "$pkgname.conf.example" "$pkgdir/etc/sensors/$pkgname.conf.example"

  # Daemon PID file
  #echo 'pid_file /run/$pkgname.pid' >> "$pkgdir/etc/sensors/$pkgname.conf.example"

  # One-Wire FileSystem files
  install -Dm644 "owserver.service" "$pkgdir/usr/lib/systemd/system/owserver.service"
  install -Dm644 "owserver.socket" "$pkgdir/usr/lib/systemd/system/owserver.socket"
  install -Dm644 "owfs.conf.example" "$pkgdir/etc/sensors/owfs.conf.example"

  # License
  install -Dm644 "LICENSE" "$pkgdir/usr/share/licenses/$pkgname/LICENSE"

}
