## Resumo

Lightsail simplifica a hospedagem de aplicativos web por meio de servidores virtuais privados (VPS's), armazenamento e rede simplificados. Ideal para pequenos projetos (blogs e sites básicos).

## Utilização

Console de Gerenciamento da AWS > Amazon Lightsail
- Tipo (instância, container, banco de dados, armazenamento e etc)
- Instância
    - Pensando em ambiente produtivo, recomenda-se configurar o IP estático.
    - Pensando em divulgação do conteúdo, pode-se utilizar o [namecheap](https://www.namecheap.com/) para criação de um domínio.
    - É obrigatório preencher localidade e imagem (os | os + app).
    - O firewall já vem configurado para as portas 22 (SSH) e 80 (HTTP), mas é possível eliminá-las e/ou incluir novas tanto para IPv4 quanto para IPv6.
    - É possível criar um snapshot (com a instância parada) e utilizá-lo na criação de outras instâncias.
    - Para um ambiente de alta disponibilidade o mínimo a ser considerado são 2 máquinas que podem ser ampliadas.
- Load Balance é possível configurar alertas para determinadas condições (quantidade de instâncias inferior ao parametrizado, por exemplo).
- Storage (bucket ou disk)
    - Bucket com nome único globalmente
    - Para disco, após criado é preciso anexá-lo à instância e configurar (particionar, instalar o file system e montar)
        - `fdisk /dev/xv… ; mkfs.ext4 /dev/xv..`
    - Incluir no fstab para que a montagem seja automática após a reinicialização
        - Executar `sudo mount -a` para montar tudo que estiver no fstab sem reiniciar a máquina
- Container
    - É obrigatório preencher localidade
    - Definir imagem do registry e porta (conforme Dockerfile da imagem)
    - É possível:
        - Utilizar o Container Services que irá criar 1 ou mais nodes para gerenciar os seus containers
        - Criar uma VM , instalar o docker e fazer deploy do seu container.