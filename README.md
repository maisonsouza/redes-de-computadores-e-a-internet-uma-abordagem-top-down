# Anotações do livro Rede de Computadores uma Abordagem Top Down
![](https://images-na.ssl-images-amazon.com/images/I/71afmekhEBL.jpg)

## Autores: Kurose | Ross 6º Edição
`Sobre os autores ambos são professores universitários americanos com vasta exeperiência em Redes de Computadores.
ISBN: 9788581436777`

### Prefácio
`Alguns códigos e exercícios em Java foram substituídos pela linguagem Python.
A Maioria dos livros de Redes utiliza uma abordagem de camadas bottom-up, porém este livro utiliza a abordagem top-down
A Internet em foco
Arquitetura de 5 camadas: aplicação, transporte, rede, enlace e física.
Os 5 primeiros capítulos são a base do conhecimento do livro`

### Redes de Computadores e a Internet.
- 1.1 O que é a Internet?
```
R: É uma rede de redes. Um a infraestrututa de redes que fornece serviços para aplicaçes distribuídas que são executadas nos sistemas finais. 
```
  - 1.1.1 Uma descrição dos componentes da rede
  ```
  Hospedeiros ou sistemas finais(hosts) são os equipamentos que estão ligados à Internet.
  Sistemas finais são conectados entre si por enlaces e comutadores.
  Tipos de enlaces de comunicação(meio físico):cabos coaxiais, fibras óticas e ondas de rádio. 
  Comutadores de pacotes são roteadores e comutadores da camada de enlace(switches).
  Roteadores (Núcleo da rede)
  Switches(Redes de acesso).
  Rota ou caminho é a sequência de enlaces de comunicação que um pacote percorre desde o sistema final remetente até o sistema final receptor.
  Provedores de Serviços de Internet(ISP)
  Protocolos controlam o envio e o recebimento de informações.
  O TCP(Transmission Control Protocol) Protocolo de Controle de Transmissão e o IP(Internet Protocol) Protocolo da Internet são os dois mais importantes da Internet.
  O protocolo IP especifica o formato dos pacotes que são enviados e recebidos entre roteadores e sistemas finais.
  Os principais protocolos da internet são conhecidos como TCP/IP.
  RFC são documentos padres que contém detalhes técnicos e detalhados sobre o funcionamento dos protocolos.
  
  ```
  - 1.1.2 Uma descrição do serviço
  ```
  Aplicaçes distribuídas são aplicaçes que envolvem diversos sistemas finais que trocam informações mutuamente.
  API(Interface de programação de aplicação) 
  ```
  - 1.1.3 O que é um protocolo?
  ```
  Um protocolo define o formato ea ordem das mensagem trocadas entre duas ou mais entidades comunicantes, bem como as ações realizadas na transmissão e ou no recebimento de uma mensagem ou outro evento.
  ```
- 1.2 A periferia da Internet
```
Na periferia da rede ficam os sistemas finais ou hosts.
Sistemas finais podem ser subdivididos em duas categorias: cliente e servidor.
```
  - 1.2.1 Redes de acesso
  ```
  Acesso doméstico: DSL, cabo, FTTH, discado e satélite.
• um canal downstream de alta velocidade, com uma banda de 50 kHz a 1 MHZ;
• um canal upstream de velocidade média, com uma banda de 4 kHz a 50 kHz;
• um canal de telefone bidirecional comum, com uma banda de 0 a 4 kHz.
Acesso Ethernet e Wi-fi.
Acesso sem fio longa distância: 3G E LTE.
  ```
  - 1.2.2 Meios físicos
  ```
  Par de fios de cobre trançado, cabo coaxial, cabo de fibra ótico multimodo, espectro de rádio terrestre e espectro de       rádio por satélite.
  São enquadrados em duas categorias: meios guiados e meios não guiados.
  Meios guiados as ondas são dirigidas ao longo de um meio sólido.
  Meios não guiados as ondas se propagam na atmosfera e no espaço.
  Par de fios de cobre são mais utilizados.
  ```
- 1.3 O núcleo da rede
```
Comutadores de pacotes e enlaces que interconectam os sistemas finais da Internet.
```
  - 1.3.1 Comutação de pacotes
  ```
  Pacotes são mensagens longas fragmentadas em pequenas porçoes de dados menores.
  Os roteadores só começam a transmitir o pacote depois de terem recebido o pacote por completo.
  Essas transmisses possuem atrasos.
  Atrasos de fila e perda de pacote.
  Perda de pacote é quando um apcote que está chegando ou um dos que já estão na fila é descartado.
  Roteadores possuem uma tabela de encaminhamento.
  ```
  - 1.3.2 Comutação de circuitos
  ```
  Conexão fim-a-fim dedicada entre hospedeitos.
  Multiplexação por divisão de frequência FDM
  Multiplexação por divisão do tempo TDM
  Comutação de pacotes x Comutação de circuitos.A comutação de pacotes tem o mesmo desempenho da comutação de circuitos, mas   o faz para mais de três vezes o número de usuários.
  Comutação de pacotes alocação por demanda.
  ```
  - 1.3.3 Uma rede de redes
    ```
    Pop é um grupo de um ou mais roteadores no mesmo local na rede do provedor.
    Multi-home é a conexão em dois ou mais ISPs provedores.
    IXP(Internet Exchange Point) Ponto de troca da Internet onde os ISPs podem se emparelhar.
    Rede de provedores de conteúdo - Google
    ```
- 1.4 Atraso, perda e vazão em redes de comutação de pacotes
  - 1.4.1 Uma visão geral de atraso em redes de comutação de pacotes
  ```
  atraso de processamento nodal = O tempo exigido para examinar o pacote e determinar para onde direcioná-lo é parte do       atraso de processament.
  atraso de fila = O pacote recebe um atraso de fila enquanto espera para ser transmitido no enlace.
  atraso de transmissão = Caracteriza o tempo que um pacote leva para ser trasmitido e processado.
  atraso de propagação = é o tempo que leva para propagar o bit desde o ínicio do enlace até o roteador.
  atraso nodal total que é a soma de todos os atrasos acima.
  ```
  - 1.4.2 Atraso de fila e perda de pacote
  ```
   Perda de pacote quando um pacote chega a uma fila cheia o roteador o descarta, e ele é perdido e pode ser retransmitido.
  ```
 
  - 1.4.3 Atraso fim a fim
  ```
     Atraso fim a fim = é o atraso além de um único roteador, considerando origem e destino final.
     Traceroute software que mostra a rota completa de 3 pacotes de testes enviados entre sistemasi finais.
     PingPlotter programa com uma interface gráfica para traceroute.
  ```

  - 1.4.4 Vazão nas redes de computadores
  ```
  Valor da transferência entre hospedeiros.(Vazão instantânea, média,fim-a-fim)
  ```
- 1.5 Camadas de protocolo e seus modelos de serviço (Pág35)
  - 1.5.1 Arquitetura de camadas
```
  Uma arquitetura em camadas nos permite discutir uma parcela específica e bem definida de um sistema grande e complexo.
  Modelo de serviço são os serviços que uma camada oferece à camada acima dela.
  A pilha de protocolos da internet é formada por 5 camadas: física, enlace, rede, transmissão e aplicação.
  A camada de aplicação é onde residem as aplicações de rede e seus protocolos.(HTTP, FTP, SMTP).
  O modelo de referência OSI possui 7 camadas com a adição das camadas de apresentação e sessão.
  O modelo OSI foi definido pela ISO.
  Na camada de aplicação o pacote  denominado mensagem.
  Camada de transporte da Internet carrega mensagens da camada de aplicação entre os lados do cliente e servidor de uma aplicação.(TCP, UDP).
  Na camada de trasporte o pacote é denominado segmento.
A camada de rede é responável pela movimentação de um hospedeiro para outro, de pacotes da camada de rede conhecidos como datagramas.(IP)
  Camadas de enlace(Ethernet, wifi) 
  Pacotes na camada de enlace são denominados quadros.
  Camada física movimentar os bits individuais que estão dentro do quadro de um nó para o seguinte.
  Camada de apresentação  prover serviços que permitam que as aplicações de comunicação interpretem o significado dos dados   trocados.(Compressão e codificaçao de dados).
  A camada de sessão provê a delimitação e soncronização da troca de dados incluidndo os meios de construir um esquema de     pontos de verificaçao e de recuperaçao. 
  ```
  - 1.5.2 Encapsulamento
  ```
  Cada camada encapsula os dados da camada acima.(mensagem, segmento, datagrama, quadro)
  ```
- 1.6 Redes sob ameaça
```
Redes de computadores sofrem ameaças constantes.Malwares, spywares, worms.
Ataque DOS ou recusa de serviço(Ataque de vulnerabilidade, Inundação na largura de banda larga, inundaçaõ de conexão)
Ataque DDOS(Ataque distribuído)
Analisadores de pacotes.
Ip spoofing
man-in-the-middle
```
- 1.7 História das redes de computadores e da Internet
  - 1.7.1 Desenvolvimento da comutação de pacotes: 1961-1972
  O surgimento dos primeiros computadores de pacotes.
  ArpaNET
  
  - 1.7.2 Redes proprietárias e trabalho em rede: 1972-1980
  * Protocolo TCP
  - 1.7.3 Proliferação de redes: 1980-1990
  * Ligações entre universidades americanas.
  * TCP/IP
  
  - 1.7.4 A explosão da Internet: a década de 1990
  * Surgimento da Web
  * Surgimento de vários serviços (Email, mensagens, mp3, torrent)
  
  - 1.7.5 O novo milênio
  * Redes sociais.
  * Aplicaçes em Nuvem.
  
- 1.8 Resumo
- Exercícios de fixação e perguntas
- Problemas
- Wireshark Lab
- Entrevista: Leonard Kleinrock




