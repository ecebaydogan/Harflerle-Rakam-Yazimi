# Harflerle-Rakam-Yazimi
Python dilinde harflerle seçilen rakamları ekran çıktısı olarak belirler.
def harf_sifrele(harf):
    harf = harf.lower()
    if 'a' <= harf <= 'c':
        return str(ord(harf) - ord('a') + 1)
    elif harf == 'ç':
        return str(ord(harf) - ord('ç') + 4)
    elif 'd' <= harf <= 'g':
        return str(ord(harf) - ord('d') + 5)
    elif harf == 'ğ':
        return str(ord(harf) - ord('ğ') + 9)
    elif harf == 'h':
        return str(ord(harf) - ord('h') + 10)
    elif harf == 'ı':
        return str(ord(harf) - ord('ı') + 11)
    elif 'i' <= harf.lower() <= 'o':
        return str(ord(harf.lower()) - ord('i') + 12)
    elif harf == 'ö':
        return str(ord(harf) - ord('ö') + 19)
    elif harf == 'p':
        return str(ord(harf) - ord('p') + 20)
    elif harf == 'r':
        return str(ord(harf) - ord('r') + 21)
    elif harf == 's':
        return str(ord(harf) - ord('s') + 22)
    elif harf == 'ş':
        return str(ord(harf) - ord('ş') + 23)
    elif 't' <= harf <= 'u':
        return str(ord(harf) - ord('t') + 24)
    elif harf == 'ü':
        return str(ord(harf) - ord('ü') + 26)
    elif harf == 'v':
        return str(ord(harf) - ord('v') + 27)
    elif harf == 'y':
        return str(ord(harf) - ord('y') + 28)
    elif harf == 'z':
        return str(ord(harf) - ord('z') + 29)
    elif harf == ' ':
        return str(ord(harf) - ord(' ') + 30)
    elif harf == '.':
        return str(ord(harf) - ord('.') + 31)
    else:
        return harf



def metni_sifrele(metin):
    sifrelenmis_metin = ""

    for karakter in metin.lower():  
        sifrelenmis_metin += harf_sifrele(karakter) + '.'
    return sifrelenmis_metin



def kontrol():
    try:
        with open("C:/Users/Admin/Desktop/metin.txt", 'r', encoding='utf-8') as metin_dosyasi:
            metin = metin_dosyasi.read()

        sifrelenmis_metin = metni_sifrele(metin)

        with open("C:/Users/Admin/Desktop/sonuç.txt", 'w', encoding='utf-8') as sonuc_dosyasi:
            sonuc_dosyasi.write(sifrelenmis_metin)

        print("sonuç.txt dosyasına aktarıldı")

    except Exception as Hatalar:
        print(f"Hata: {Hatalar}")

kontrol()
