# robonomics-resources

# Install Robonomics using docker

1. Install docker  
   Установка докера
`sudo apt update && sudo apt install -y docker.io`

2. Run docker container  
   Запуск докер контейнера  
Replace the `NICKNAME` with the nickname that you selected when you sign up (google form)  
Меняем `NICKNAME` на свой никнэйм, который вы указывали при регистрации в гугл форме  
Replace the `ETH_ADDRESS` with the ETH address that you selected when you sign up (google form)  
Меняем `ETH_ADDRESS` на свой адрес, который указывали при регистрации  

```
mkdir ~/robonomics; \
docker run -dit --name robonomics-NICKNAME \
-p 9947:9944 -p 9937:9933 -p 30337:30333 \
--volume /root/robonomics:/root/.local/share/robonomics \
--restart=always c29r3/robonomics-node:latest \
/root/source/robonomics --chain parachain --name "NICKNAME | ETH_ADDRESS"
```

3. Check that container started properly  
Проверяем что контейнер запустился корректно (смотрим логи)  
`docker logs -f robonomics-NICKNAME`  
If you successfully launch, you'll see something similar  
При успешном запуске вы увидите похожий вывод  
![alt text](https://github.com/c29r3/robonomics-resources/blob/master/2020-08-20_23-39.png)
