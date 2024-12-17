import pygame
import random
import sys
import string
import requests
from bs4 import BeautifulSoup

def turkce_kelime_listesi():
    url = "https://tr.wiktionary.org/wiki/Ek:Türkçe_temel_sözlük_(kullanım_sıklığına_göre)"
    response = requests.get(url)
    response.raise_for_status()  # İstek başarısız olursa hata fırlatır

    soup = BeautifulSoup(response.text, 'html.parser')
    kelimeler = []

    # 'mw-content-ltr' sınıfına sahip div içindeki <ol> etiketlerini bul
    for ol in soup.find_all('ol'):
        for li in ol.find_all('li'):
            a = li.find('a')
            if a and 'title' in a.attrs:
                kelimeler.append(a['title'])

    return kelimeler

# Örnek kullanım
kelime_listesi = turkce_kelime_listesi()

def kelime_al():
    """Oyun için rastgele bir kelime al."""
    return random.choice(kelime_listesi).lower()

def kelime_goster(kelime, tahmin_edilen_harfler):
    """Tahmin edilen harflerle kelimeyi ve alt çizgileri göster."""
    return " ".join([harf if harf in tahmin_edilen_harfler else "_" for harf in kelime])

def adam_ciz_grafik(hak, ekran):
    """Adam çizimini grafiksel olarak çizer."""
    # Direk çizimi
    pygame.draw.line(ekran, (0, 0, 0), (300, 50), (300, 300), 5)  # Ana direk
    pygame.draw.line(ekran, (0, 0, 0), (200, 50), (300, 50), 5)  # Üst direk
    pygame.draw.line(ekran, (0, 0, 0), (200, 50), (200, 100), 5)  # İp

    if hak <= 5:  # Kafa
        pygame.draw.circle(ekran, (0, 0, 0), (200, 125), 25, 5)
    if hak <= 4:  # Gövde
        pygame.draw.line(ekran, (0, 0, 0), (200, 150), (200, 225), 5)
    if hak <= 3:  # Sol kol
        pygame.draw.line(ekran, (0, 0, 0), (200, 175), (150, 200), 5)
    if hak <= 2:  # Sağ kol
        pygame.draw.line(ekran, (0, 0, 0), (200, 175), (250, 200), 5)
    if hak <= 1:  # Sol bacak
        pygame.draw.line(ekran, (0, 0, 0), (200, 225), (150, 275), 5)
    if hak == 0:  # Sağ bacak
        pygame.draw.line(ekran, (0, 0, 0), (200, 225), (250, 275), 5)

def giris_ekrani(ekran):
    """Giriş ekranını oluşturur."""
    ekran.fill((255, 255, 255))  # Beyaz arka plan
    font = pygame.font.Font(None, 30)

    # Başlık
    baslik = font.render("Adam Asmaca Oyununa Hoş Geldiniz!", True, (0, 0, 0))
    ekran.blit(baslik, (50, 100))

    # Oyun oyna butonu
    pygame.draw.rect(ekran, (173, 216, 230), (200, 300, 200, 50))  # Yeşil buton
    pygame.draw.rect(ekran, (0, 0, 0), (200, 300, 200, 50), 3)  # Siyah kenarlık
    buton_yazi = font.render("Oyun Oyna", True, (255, 255, 255))
    ekran.blit(buton_yazi, (225, 310))

    pygame.display.flip()

def oyun_penceresi(kelime, tahmin_edilen_harfler, hak, ekran, mesaj="", tekrar_oyna_butonu=False, hatali_harfler=set()):
    """Oyun ekranını güncelle ve çiz."""
    ekran.fill((255, 255, 255))  # Beyaz arka plan

    # Adam çizimi
    adam_ciz_grafik(hak, ekran)

    font = pygame.font.Font(None, 30)

    # Kelimenin durumu
    kelime_yazi = font.render(kelime_goster(kelime, tahmin_edilen_harfler), True, (0, 0, 0))
    ekran.blit(kelime_yazi, (50, 350))

    # Hatalar
    hak_yazi = font.render(f"Kalan Hak: {hak}", True, (0, 0, 0))
    ekran.blit(hak_yazi, (50, 20))

    # Hatalı harfler
    hatali_yazi = font.render(f"Hatalı Harfler: {', '.join(hatali_harfler)}", True, (255, 102, 102))
    ekran.blit(hatali_yazi, (300, 20))

    # Mesaj
    if mesaj:
        mesaj_yazi = font.render(mesaj, True, (255, 0, 0))
        ekran.blit(mesaj_yazi, (50, 250))

    # Tekrar oyna butonu
    if tekrar_oyna_butonu:
        pygame.draw.rect(ekran, (124, 205, 124), (200, 300, 200, 50))  # Yeşil buton
        pygame.draw.rect(ekran, (0, 0, 0), (200, 300, 200, 50), 3)  # Siyah kenarlık
        buton_yazi = font.render("Tekrar Oyna", True, (255, 255, 255))
        ekran.blit(buton_yazi, (241, 315))
        
        # Kaybedilen kelimeyi göster
        if hak == 0:
            kayip_yazi = font.render(f"Kaybettiniz! Kelime: {kelime}", True, (255, 102, 102))
            ekran.blit(kayip_yazi, (50, 400))

    pygame.display.flip()

def adam_asmaca():
    """Adam asmaca oyununu başlatan ana fonksiyon."""
    pygame.init()

    # Pencere ayarları
    ekran = pygame.display.set_mode((600, 500))
    pygame.display.set_caption("Adam Asmaca")

    # Giriş ekranı
    giris_ekraninda = True
    while giris_ekraninda:
        giris_ekrani(ekran)
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                pygame.quit()
                sys.exit()

            if event.type == pygame.MOUSEBUTTONDOWN:
                x, y = event.pos
                if 200 <= x <= 400 and 300 <= y <= 350:
                    giris_ekraninda = False

    while True:
        kelime = kelime_al()
        tahmin_edilen_harfler = set()
        hatali_harfler = set()
        hak = 6

        oyun_devam = True

        while oyun_devam:
            oyun_penceresi(
                kelime,
                tahmin_edilen_harfler,
                hak,
                ekran,
                mesaj=("Tebrikler! Kazandınız!" if "_" not in kelime_goster(kelime, tahmin_edilen_harfler) else ""),
                tekrar_oyna_butonu=(hak == 0 or "_" not in kelime_goster(kelime, tahmin_edilen_harfler)),
                hatali_harfler=hatali_harfler
            )

            for event in pygame.event.get():
                if event.type == pygame.QUIT:
                    pygame.quit()
                    sys.exit()

                if event.type == pygame.KEYDOWN and hak > 0 and "_" in kelime_goster(kelime, tahmin_edilen_harfler):
                    tahmin = event.unicode.lower()

                    if len(tahmin) != 1 or not tahmin.isalpha():
                        continue

                    if tahmin in tahmin_edilen_harfler or tahmin in hatali_harfler:
                        continue

                    if tahmin in kelime:
                        tahmin_edilen_harfler.add(tahmin)
                    else:
                        hatali_harfler.add(tahmin)
                        hak -= 1

                if event.type == pygame.MOUSEBUTTONDOWN:
                    x, y = event.pos
                    if 200 <= x <= 400 and 300 <= y <= 350 and (hak == 0 or "_" not in kelime_goster(kelime, tahmin_edilen_harfler)):
                        oyun_devam = False

if __name__ == "__main__":
    adam_asmaca()
