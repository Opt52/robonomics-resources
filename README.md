# robonomics-resources

#  Run Robonomics using docker

1. Install docker  
`sudo apt update && sudo apt install -y docker.io`

2. Run docker container  
Replace the `NICKNAME` with the nickname which will be displayed in telemetry  
Replace the `ETH_ADDRESS` with the ETH address which will be displayed in telemetry  

```
mkdir ~/robonomics; \
docker run -dit --name robonomics-NICKNAME \
-p 9947:9944 -p 9937:9933 -p 30337:30333 \
--volume /root/robonomics:/root/.local/share/robonomics \
--restart=always c29r3/robonomics-node:v0.21.0 \
/root/source/robonomics --chain parachain --name "NICKNAME | ETH_ADDRESS"
```

3. Check that container started properly  
`docker logs -f robonomics-NICKNAME`  
If you successfully launch, you'll see something similar  
![alt text](https://github.com/c29r3/robonomics-resources/blob/master/2020-08-20_23-39.png)  

4. Find your node by a nickname\address in telemetry at https://telemetry.polkadot.io/#list/Robonomics  

