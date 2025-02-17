## Tavsiye Edilen Sistem Gereksinimleri
- CPU: 4+ ÇEKİRDEK
- RAM: 4+ GB (Önerilen 8)
- SSD: Kodda gireceğiniz boyut  ile bağlantılı gireceğiniz değer dışında +50GB yer olmalı. (Kodda Plot Size:1GB girilecekse HDD'nin en az 51GB olmalı ki ben sıkıntılara karşı bunun 70-80GB den aşağı olmamasını ÖNERİYORUM.)
- İşletim Sistemi: Ubuntu 20.04LTS

## Kurulum Adımları ve Kodları
- Daha önce testlere katıldıysanız aynı cüzdanı kullanın. Eğer ilk defa katılıyorsanız 2. adımdan cüzdan oluşturun.
- https://polkadot.js.org/extension/ sitesinden cüzdan kurulumu yapıp cüzdan oluşturuyoruz ve bize verdiği gizli kelimeleri kesinlikle saklıyoruz. Ayrıca .json dosyasını da indirip yedeklemeyi unutmayın.
- Daha sonra aşağıdaki kodlarla adım adım yükleme işlemine geçiyoruz.Script ile kurulum kısa bir zamanda tamamlanıyor o yüzden yükleme adımı için onu kullanıyoruz.

-Kurulumdan önce ÖNEMLİ bir nokta var . Eğer 3c'de node çalıştırıyorsanız ve 3d'ye geçmek istiyorsanız her şeyin öncesinde alttaki kodu çalıştırmalı ve vereceği uyarılara y diyerek temizleme işlemini yapmalısınız.
```
./subspace-cli-ubuntu-x86_64-v3-v0.1.12 wipe
```

-Kurulumu aşağıdaki kodlarla başlatıyoruz ve root kullanısında olun.
```
wget -q -O gemini3d.sh https://raw.githubusercontent.com/okannako/subspacenetwork/main/gemini3d.sh && chmod +x gemini3d.sh && sudo /bin/bash gemini3d.sh
```
- Yükleme bittikten sonra öncelikle aşağıdaki kodlarla Tmux yükleyip bir tmux sayfası açıyorsunuz. Tmux olmazsa sürekli çalışmaz.
 ```
 cd
 sudo apt install tmux
 tmux new -s subspace
 ```
- Sayfayı açtıktan sonra ilk olarak ayarlarımızı yapmak için alttaki kodu çalıştırıyoruz.
```
./subspace-cli-ubuntu-x86_64-v3-v0.3.3-alpha init
```
   -Burada sırayla bize sorduğu sorulara şu cevapları veriyoruz.
    1-) Cüzdan adresimizi soruyor, subspace adresimizi giriyoruz.
    2-) Node isminizi soruyor, istediğiniz bir ismi verebilirsiniz, listede bu isminiz görünecek.
    3-) Enter
    4-) Plot Size sorusunda minimum değer olarak 1GB (Değer girme şekli böyle olmalı yoksa hata alırsınız) girebilirsiniz, maximum yok.
    5-) Enter
    6-) Enter
    
- Şimdi aşağıdaki kodla da nodenumuzu başlatıyoruz. Bir süre sonra ```Node started successfully!``` uyarısı verecek ve sisteme eşitlenmeye başlayacak. Bu süre günlerde sürebilir.
```
./subspace-cli-ubuntu-x86_64-v3-v0.3.3-alpha farm
```
- Bundan sonra Tmux ekranını direkt kapatabilirsiniz ya da arkaya atmak için ```ctri+b d``` kombinasyonunu kullanabilirsiniz. Tekrar girmek içinse ```tmux attach -t subspace``` kodunu kullanabilirsiniz.

## Node Silmek
 -Node silmek için tmux ekranında ```ctrl+c``` yaptıktan sonra aşağıdaki kodları girmeniz yeterli

```
rm -rf ~/.local/share/subspace-cli*
rm -rf /etc/systemd/system/subspaced*
rm -rf /usr/local/bin/subspace-cli*
```

- Ödül toplamaya başladığınızda cüzdan adresinizi siteden aratabilirsiniz.
     - https://explorer.subspace.network/#/gemini-3d/accounts
- Başlatma işlemini yaptıktan sonra şu sitede isminizin bir süre sonra görünmesi gerekiyor.
     - https://telemetry.subspace.network/#list/0x7f489750cfe91e17fc19b42a5acaba41d1975cedd3440075d4a4b4171ad0ac20
- Son olarak aşağıdaki siteye giderek ve cüzdanımıza izin vererek blok imzaladıkça kazandığınımız ödülü görebiliriz.
     - https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Feu-0.gemini-3d.subspace.network%2Fws#/explorer



