# Maintainer: Andrey Mivrenik <gim at fastmail dot fm>
pkgbase=phpbb3-i18n
pkgver=3.0.12
pkgrel=5
pkgdesc="Language Pack Collection for phpBB3"
arch=('any')
url="https://www.phpbb.com/languages/"
license=('GPL')
depends=("phpbb3=$pkgver")

pkgname=()
source=()
_url=https://www.phpbb.com/customise/db/download

_languages=(
    'de             "Casual German"         "german_casual_honorifics"              "3_0_12"    91416'
    'de-x-formal    "Formal German"         "german_formal_honorifics"              "3_0_12"    91421'
    'es             "Casual Spanish"        "spanish_casual_honorifics"             "1_0_6"     92696'
    'es-x-formal    "Formal Spanish"        "spanish_formal_honorifics"             "1_0_6"     92601'
    'es-ar          "Argentinian Spanish"   "argentinian_spanish_formal_honorifics" "1_0_2"     91866'
    'es-mx          "Mexican Spanish"       "mexican_spanish_casual_honorifics"     "1_0_5"     92146'
    'fr             "French"                "french"                               "1_4_1"     91611'
    'it             "Italian"               "italian"                              "1_2_2"     91861'
    'nl             "Casual Dutch"          "dutch_casual_honorifics"               "1_0_13_1"  91751'
    'nl-x-formal    "Formal Dutch"          "dutch_formal_honorifics"               "1_0_5"     91666'
    'ru             "Russian"               "russian"                              "1_0_11"    91291'
    'sv             "Swedish"               "svenska"                              "1_4_8"     94846'
    'ua             "Ukrainian"             "ukrainian"                            "1_0_9"     92276'
    'us             "American English"      "american_english"                     "1_3_0"     91116'
)

for _lang in "${_languages[@]}"; do
    _locale=${_lang%% *}
    _pkgid=${_lang##* }
    _pkgname=phpbb3-i18n-${_locale}

    # Probably a bit ugly way to do this though
    _ln=${_lang#*\"}
    _ln=${_ln%%\"*\"*\"*}
    _lnname=${_lang#*\"*\"*\"}
    _lnname=${_lnname%%\"*\"*\"*}

    pkgname+=($_pkgname)
    source+=("$_url/id_$_pkgid")
    eval "package_$_pkgname() {
        pkgdesc='$_ln Language Pack for phpBB3'
        url='https://www.phpbb.com/customise/db/translation/$_lnname/'
        _package $_lang
    }"
done

_package() {
    install -d  ${pkgdir}/usr/share/webapps/
    # There are some mainstream packaging issues.
    # https://tracker.phpbb.com/browse/CUSTDB-616
    cp -r $(find "$srcdir/${3}_${4}" -name 'language' -printf '%h\n') ${pkgdir}/usr/share/webapps/phpbb3
}

md5sums=('9b06cdad852e61779775c0288e65fa7c'
         'd209f53d73e9843096e62115b40531eb'
         '2ae2238ebcd70af6f05beaeaa52e35d9'
         'a4181c508c0631441a5105fd632b94e3'
         '57a47e583f0359eb4609b908ca7ac7be'
         'e89db8a2982e0a2e9730333d823ad76c'
         '27d2cf5daef6ffed0ef6bfc3871fb150'
         '156de7eba20d9496790d2df228d40bd4'
         'af2c50989e1fe6b46f3dc3f105553eb0'
         '186577da55926e6061d06310cebfa11c'
         '45aa4adc3f7bdd1b79cd67d8e6a52c2e'
         'e0044422e5fc5436169eff2a9e726eb0'
         'ede3238ac332e28a9651aead37437da2'
         '24f7ac6977b46051b1af782f42d2545c')
# vim:set ts=4 sw=4 et:
