## Padrões que quero adotar em microservices nos nossos projetos
* Dentre as razões da arquitetura de microservices - distribuída -, está a condição em que seja possivel desenvolver, implantar e escalar cada serviço independentemente, o que por sua vez, melhora a produtividade, segurança e escalabilidade.

* Importante lembrar que a separação em microservices deve ser feita com base nas fronteiras de negócios, e não necessariamente nas relações entre as entidades do banco de dados. Levando em consideração casos em que tenhamos funcionalidades distintas dentro do sistema.

* Memcached - Cache de dados em memória
* Desenvolver tecnologias proprietarias para lidar com bilhões de dados: Como Sharding do instagram, que permite a distribuição de dados em diferentes servidores, e o Hyperlapse, que é um sistema de indexação em tempo real que ajuda a melhorar a performance de pesquisas em grandes conjuntos de dados.

* Questões para lidar no GATEWAY CENTRAL: utilizar um gateway central como proxy é uma boa prática em arquiteturas baseadas em microservices, pois permite a centralização da lógica de roteamento e distribuição de requisições, simplificando a comunicação entre os diferentes serviços. Além disso, o gateway central pode oferecer recursos de segurança, autenticação e controle de acesso, melhorando a governança da arquitetura.

No entanto, em sistemas com milhões de requisições, é importante garantir que o gateway central seja escalável e tenha um alto desempenho para lidar com o volume de tráfego. Algumas técnicas que podem ser utilizadas para melhorar a performance do gateway central incluem:

Cache de resposta: Utilizar um cache de resposta pode ajudar a reduzir o tempo de resposta do gateway central para requisições frequentes, melhorando a performance geral do sistema.

Balanceamento de carga: Utilizar um balanceador de carga pode ajudar a distribuir o tráfego entre vários instâncias do gateway central, melhorando a disponibilidade e a performance do sistema.

Escalonamento horizontal: Utilizar múltiplas instâncias do gateway central em um cluster pode ajudar a aumentar a capacidade de processamento e melhorar a escalabilidade do sistema.

Otimização de código: Utilizar técnicas de otimização de código e arquitetura pode ajudar a melhorar o desempenho do gateway central, reduzindo o tempo de processamento de requisições e melhorando a eficiência do sistema como um todo.

Em resumo, utilizar um gateway central como proxy é uma boa prática em arquiteturas baseadas em microservices, mas é importante garantir que o gateway seja escalável e tenha um alto desempenho para lidar com grandes volumes de tráfego. É possível melhorar a performance do gateway central utilizando técnicas como cache de resposta, balanceamento de carga, escalonamento horizontal e otimização de código.