Zeeka Network--Bazuka

![image](https://user-images.githubusercontent.com/101149671/188958599-67a3b79f-9dc1-450f-b2fd-4461598b9100.png)

<h1 align="center"> Selamlar, bu repoda Zeeka Network node kurulum rehberi ile karşınızdayım </h1>

 * Cosmos dışı bir proje olduğu için kurmanızı öneririm

 * Ödüllü değil, ödüllü testnet yakında

 * Hocam sunucum boşta ne kuralım diyenler için

 * Sorularınız için: [Sohbet kanalı](https://discord.gg/jZBhUBf7)

## Sistem gereksinimleri:
```
2 CPU
2 RAM
50 SSD (fazla bile)
```

## libssl-dev kurarak başlıyoruz:
```
sudo apt update && sudo apt upgrade -y
sudo apt install curl tar wget clang pkg-config libssl-dev jq build-essential bsdmainutils git 
make ncdu gcc git jq chrony liblz4-tool -y
```

## cmake kuruyoruz:
```
sudo apt install cmake -y
```

## rustup'ı kuruyoruz:

 * Kurulum tamamlandıktan sonra 1'e basıp enterliyoruz

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
![image](https://user-images.githubusercontent.com/101149671/188959152-b52fae46-8004-4fa5-9ca3-e0758c6f3301.png)

## git clone çekiyoruz:
```
git clone https://github.com/zeeka-network/bazuka
```

## Cargo'yu yüklüyoruz:
```
apt install cargo -y
```

## path'i kuruyoruz:

```
cd
cd bazuka && cargo install --path .
```

## Görselde ki gibi bir uyarı alırsanız bu komutu
```
if [ -d "$HOME/.cargo/bin" ] ; then
  PATH="$PATH:$HOME/.cargo/bin"
fi
```

![image](https://user-images.githubusercontent.com/101149671/188959534-3ea71c13-fe85-430b-8cdb-8c0650c982ec.png)

## seedi ekliyoruz:
```
bazuka init --seed 38b4d78c7d6582fb170f6c19330a7e37e6964212@rues.forum.info:8765 --network debug --node 127.0.0.1:8765
```

## nodu kuruyoruz:

 * your external ip kısmını sunucu ip'inizi girin ve daha sonra parantezleri kaldırın

```
bazuka node --listen 0.0.0.0:8765 --external [your external ip]:8765 \
  --network debug --db ~/.bazuka-debug --bootstrap [bootstrap node 1] --bootstrap [bootstrap node 2] ...
```

## nodu çalıştırıyoruz:
```
apt install screen
```
```
screen -S bazuka
```
```
bazuka node
```

## Nodunuz bu şekilde çalışır olacak:

 * Cüzdanlarınızı kaydedin.

![image](https://user-images.githubusercontent.com/101149671/188964602-895b445c-8829-4d72-bb5a-ed57a0a41f84.png)

## Explorer [Linki](http://152.228.155.120:8000/)
