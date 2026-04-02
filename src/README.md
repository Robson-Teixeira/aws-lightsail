## Resumo

Lightsail simplifica a hospedagem de aplicativos web por meio de servidores virtuais privados (VPS's), armazenamento e rede simplificados. Ideal para pequenos projetos (blogs e sites básicos).

## Utilização

Console de Gerenciamento da AWS > Amazon Lightsail
- Tipo (instância, container, banco de dados, armazenamento e etc)
    - Para instâncias e pensando em ambiente produtivo, recomenda-se configurar o IP estático.
    - Para instância, e pensando em divulgação do conteúdo, pode-se utilizar o [namecheap](https://www.namecheap.com/) para criação de um domínio.
    - Para instância, é obrigatório preencher localidade e imagem (os | os + app).
    - Para instância, o firewall já vem configurado para as portas 22 (SSH) e 80 (HTTP), mas é possível eliminá-las e/ou incluir novas tanto para IPv4 quanto para IPv6.
    - Para instância, é possível criar um snapshot (com a instância parada) e utilizá-lo na criação de outras instâncias.
    - Para um ambiente de alta disponibilidade o mínimo a ser considerado são 2 máquinas que podem ser ampliadas.
- Load Balance é possível configurar alertas para determinadas condições (quantidade de instâncias inferior ao parametrizado, por exemplo).
- Storage (bucket ou disk)
    - Bucket com nome único globalmente