Camada de Transporte



A camada de transporte desempenha o papel fundamental de fornecer serviços de comunicação diretamente aos processos de aplicação que rodam em hospedeiros diferentes.

Principais protocolos de transporte da Internet são UDP e TCP.

TCP é o protocolo de transporte orientado para conexão.

Um protocolo da camada de transporte fornece comunicação lógica entre processos de aplicação que rodam em hospedeiros diferentes.

Comunicação lógica é como se os hospedeiros que rodam os processos estivessem conectados diretamente.

No lado remetende a camada de transporte converte as mensagens que receve de um processo de aplicação remetente em pacotes de camada de transporte denominados segmentos de camada de transporte.

Essa camada então passa o segmento para a de rede no sistema final remetente onde ele é encapsulado em uma pacote de camada de rede (um datagrama) e enviado ao destinatário.

TCP e UDP cada um oferece um conjunto diferente de serviços de camada de transporte.

Um protocolo da camada de transporte oferece comunicação lógica entre processos que rodam em hospedeiros diferentes, um protocolo de camada de rede fornece comunicação lógica entre hospedeiros.

Serviço confiável de transferência de dados a uma aplicação mesmo quando o protocolo subjacente da rede não é confiável..

A Internet é de uma maneira mais geral a rede TCP/IP 

UDP (User Datagram Protocol) Protocolo de Datagrama de Usuário, que oferece á aplicação solicitante um serviço confiável, orientado para conexão. O desenvolvedor da aplicação escolhe entre o UDP e o TCP ao criar sockets.

O pacote da camada de transporte é denominado segmento.

O protocolo da camada de rede tem um nome IP que quer dizer internet Protocol. O modelo de serviçõ do IP é um serviço de entrega de melhor esforço.

O ip é um serviço não confiável.

Cada hospedeiro tem um endereço IP

A ampliação da entrega hospedeiro a hospedeiro para entrega de processo a pro cesso é denominada multiplexação / demultiplexação de camada de transporte.

O UDP  e o TCP também fornecem verificação de integridade ao incluir campos de detecção de erros nos cabeçalhos de seus segmentos.

Como o IP, O UDP é um serviço não confiável.

O TCP oference transferêncuia confiável de dados.

Assim o TCP converte o serviço não confiável do IP entre sistemas finais em um serviço confiável da camada de transporte de dados entre processos. Ele também oferece controle de congestionamento, o controle de congestionamento do TCP evita que qualquer outra conexão  TCP abarrote os enlaces e roteadores entre hospedeiros comunicantes com uma quantidade excessiva de tráfego.

O tráfego UDP não é regulado

Um protocolo que fornece transferência confiável de dados e controle de congestionamento é necessariamente complexo.

Multiplexação e demultiplexação



**Exercício**



**1.O que os protocolos da camada de transporte fazem nos lados remetente e destinatário?**

R: No lado remetente, a camada de transporte converte as mensagens que recebe de um processo de aplicação remetente em pacotes de camada de transporte, denominados segmentos de camada de transporte.Essa camada, então, passa o segmento para a de rede no sistema final remetente, onde ele é encapsulado em um pacote de camada de rede (um datagrama) e enviado ao destinatário. No lado destinatário, a camada de rede extrai do datagrama o segmento de camada de transporte e passa-o para a camada de transporte que, em seguida, processa o segmento recebido, disponibilizando os dados para a aplicação destinatária.



**2.Quais os protocolos da camada de transporte da Internet?**

R: TCP e UDP.



**3.Qual a relação entre as camadas de transporte e de redes?**

R: A camada de transporte fornece comunicação lógica entre processos que rodam em hospedeiros
diferentes.



4.Considere o exemplo das moradias das crianças e numere a segunda coluna de acordo com a primeira:
1.processos                                     =                                                                (5)serviço postal
2.mensagens da apl. 					= 															   (4)Ann e Bill
3.hospedeiros 								=  															  (2)cartas nos envelopes casas
4.protocolo de transporte 		  = 															   (3)casas
5.protocolo da camada de rede = 															   (1)crianças



**5.Explique a comunicação lógica entre processos. Por que ela depende e estende os serviços da camada de rede?**

R:De maneira semelhante, os serviços que um protocolo
de transporte pode fornecer são muitas vezes limitados pelo modelo de serviço do protocolo subjacente da camada de rede. Se o protocolo de camada de rede não puder dar garantias contra atraso ou garantias de largura de banda para segmentos de camada de transporte enviados entre hospedeiros, então o protocolo de camada de transporte não poderá dar essas mesmas garantias para mensagens de aplicação enviadas entre processos. No entanto, certos serviços podem ser oferecidos por um protocolo de transporte mesmo quando o protocolo de rede subjacente não oferece o serviço correspondente na camada de rede. Por exemplo, como veremos neste capítulo, um protocolo de transporte pode oferecer serviço confiável de transferência de dados a uma aplicação mesmo quando o protocolo subjacente da rede não é confiável.



**6.Que serviços são oferecidos pelo TCP?**

R: Transferência confiável de dados, controle de congestionamento, controle de fluxo



**7.Quais os serviços não disponíveis pelos protocolos da camada de transporte da Internet?**

R: Garantias de atraso e garantias de largura de banda.


TCP E UDP

