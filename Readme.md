# Clonando imagem do Kathara
docker pull kathara/netkit_base
docker run -tid --name lsor kathara/netkit_base

# Instalando serviços na imagem clonada
docker exec -it lsor bash

	apt install isc-dhcp-server -y
	apt install squid3 -y
	apt install nginx -y

# Criando nova imagem
docker commit lsor kathara/lsor
