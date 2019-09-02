## 2 - Camada de aplicação

### 2.1 Princípios de aplicações de rede

#### 2.1.1 Arquiteturas de aplicação de rede

O núcleo do desenvolvimento de aplicação de rede é escrever programas que rodem em sistemas finais
diferentes e se comuniquem entre si.

A **arquitetura da aplicação** é projetada pelo programador e determina como a aplicação é organizada
nos vários sistemas finais.(cliente-servidor ou P2P).

Em uma **arquitetura cliente-servidor** há um hospedeiro sempre em funcionamento, denominado servidor, que atende a requisições de muitos outros hospedeiros, denominados clientes. Algumas das aplicações mais conhecidas que empregam a arquitetura cliente-servidor são **Web, FTP, Telnet e e-mail.**

Em uma **arquitetura P2P**, há uma confiança mínima (ou nenhuma) nos servidores dedicados nos centros de dados. Em vez disso, a aplicação utiliza a comunicação direta entre duplas de hospedeiros conectados
alternadamente, denominados **pares**. Eles não são de propriedade dos provedores de serviço, mas são controlados por usuários de computadores de mesa e laptops, cuja maioria se aloja em residências, universidades e escritórios. Como os pares se comunicam sem passar por nenhum servidor dedicado, a arquitetura é denominada **par a par (peer-to-peer — P2P)**. Muitas das aplicações de hoje mais populares e de intenso tráfego são baseadas nas arquiteturas P2P, incluindo **compartilhamento de arquivos** (por exemplo, BitTorrent), **aceleração de download assistida por par** (por exemplo, Xunlei), **telefonia por Internet** (por exemplo, Skype) e **IPTV** (por exemplo, KanKan e PPstream).

Uma das características mais fortes da arquitetura P2P é sua **autoescalabilidade**.



#### Comunicação entre processos

Um **processo** pode ser imaginado como um programa que está rodando dentro de um sistema final.

Quando os **processos rodam no mesmo sistema final**, comunicam-se usando comunicação interprocessos, cujas regras são determinadas pelo **sistema operacional** do sistema final.

Os processos em dois sistemas finais diferentes se comunicam trocando **mensagens** por meio da rede de
computadores.

##### Processos clientes e processos servidores

Para cada par de processos comunicantes normalmente rotulamos um dos dois processos de **cliente** e o outro, de **servidor**.

No compartilhamento de arquivos P2P, o par que envia o arquivo é rotulado de cliente e o que recebe, de servidor.tal como compartilhamento de arquivos P2P, um processo pode ser ambos, cliente e servidor.

```
No contexto de uma sessão de comunicação entre um par de processos, aquele que inicia a comunicação(isto é, o primeiro a contatar o outro no início da sessão) é rotulado de cliente. O que espera ser contatado para iniciar a sessão é o servidor.
```

##### A interface entre o processo e a rede de computadores

Um processo envia mensagens para a rede e recebe mensagens dela através de uma interface de software denominada **socket**. 

Um socket é a interface entre a camada de aplicação e a de transporte dentro de um hospedeiro.

É também denominado **interface de programação da aplicação (application programming interface — API)** entre a aplicação e a rede, visto que é a interface de programação pela qual as aplicações de rede são criadas.

##### Endereçando processos

Na Internet, o hospedeiro é identificado por seu endereço IP.

Para identificar o processo receptor, duas informações devem ser especificadas:
(1) o endereço do hospedeiro e

 (2) um identificador que especifica o processo receptor no hospedeiro de destino.Na Internet, o hospedeiro é identificado por seu endereço IP.Um endereço IP é uma quantidade de 32 bits que podemos pensar como identificando um hospedeiro de forma exclusiva.Um número de porta de destino atende a essa finalidade. Aplicações populares receberam números de porta específicos.

Essa informação é necessária porque, em geral, um hospedeiro poderia estar executando muitas aplicações de rede. Um número de porta de destino atende a essa finalidade.

Por exemplo, um servidor Web é identificado pelo número de porta 80Um processo servidor de correio (usando o protocolo SMTP) é identificado pelo número de porta 25.

#### Serviços de transporte disponíveis para aplicações

Podemos classificar, de maneira geral, os possíveis serviços segundo quatro dimensões: **transferência confiável de dados, vazão, temporização e segurança.**

#### Transferência confiável de dados

Socket é a interface entre o processo da aplicação e o protocolo de camada de transporte

Se um protocolo fornecer um serviço de recebimento de dados garantido, ele fornecerá uma **transferência confiável de dados**.Isso pode ser aceitável para aplicações tolerantes
a perda, em especial as de multimídia como áudio/vídeo em tempo real ou áudio/vídeo armazenado, que podem tolerar alguma perda de dados.

#### Vazão

É a taxa pela qual o processo remetente pode enviar bits ao processo destinatário.

Aplicações que possuam necessidade de vazão são conhecidas como aplicações sensíveis à largura de banda

aplicações elásticas podem usar qualquer quantidade mínima ou máxima que por acaso esteja disponível

#### Temporização

Citamos como exemplo o fato de que cada bit que o remetente insere no socket chega ao socket destinatário em menos de 100 ms depois. Esse serviço seria atrativo para aplicações interativas em tempo real, como a telefonia por Internet, ambientes virtuais, teleconferência e jogos multijogadores, que exigem restrições de temporização no envio de dados para garantir eficácia.

#### Segurança

um protocolo de transporte é capaz de codificar todos os dados transmitidos pelo processo remetente e, no hospedeiro destinatário, o protocolo da camada de transporte pode codificar os dados antes de enviá-los ao destinatário.

#### Protocolos de camada de aplicação

Um protocolo de camada de aplicação define como processos de uma aplicação, que funcionam
em sistemas finais diferentes, passam mensagens entre si.

protocolo de camada de aplicação da Web, HTTP

É importante distinguir aplicações de rede de protocolos de camada de aplicação, os quais são apenas um
pedaço de aplicação de rede (embora muito importante, do nosso ponto de vista!). Examinemos alguns exemplos.
A Web é uma aplicação cliente-servidor que permite aos usuários obter documentos de servidores por demanda.

O principal protocolo de camada de aplicação para o correio eletrônico é o SMTP (Simple Mail Transfer Protocol) [RFC 5321]. Assim, o SMTP é apenas um pedaço (embora importante) da aplicação de correio eletrônico.

#### Aplicações de rede abordadas neste livro

a Web, a transferência de arquivos, o correio eletrônico, o serviço de diretório e aplicações P2P



2.2 A Web e o HTTP



| Aplicação                 | Protocolo da camada de aplicação | Protocolo de transporte usado |
| ------------------------- | -------------------------------- | ----------------------------- |
| Correio eletrônico        | SMTP                             | TCP                           |
| Acesso terminal remoto    | TELNET                           | TCP                           |
| WWW                       | HTTP                             | TCP                           |
| Transferência de arquivos | FTP                              | TCP                           |
| Streaming multimídia      | RealNetworks                     | TCP OU UDP                    |
| Telefonia Internet        | VOIP                             | UDP                           |



Exercício

**1) Qual a diferença entre aplicações de rede e protocolos da camada de aplicação?**

R:É importante distinguir aplicações de rede de protocolos de camada de aplicação, os quais são apenas um pedaço de aplicação de rede (embora muito importante, do nosso ponto de vista!). Examinemos alguns exemplos.A Web é uma aplicação cliente-servidor que permite aos usuários obter documentos de servidores por demanda. A aplicação Web consiste em muitos componentes, entre eles um padrão para formato de documentos (isto é, HTML), navegadores Web (por exemplo, Firefox e Microsoft Internet Explorer), servidores Web (por exemplo, Apache e Microsoft) e um protocolo de camada de aplicação. O HTTP, protocolo de camada de aplicação da Web, define o formato e a sequência das mensagens que são passadas entre o navegador e o servidor. Assim, ele é apenas um pedaço (embora importante) da aplicação Web. Como outro exemplo, a aplicação de correio eletrônico da Internet que também tem muitos componentes, entre eles servidores de correio que armazenam caixas postais de usuários, leitores de correio (como o Microsoft Outlook) que permitem aos usuários ler e criar mensagens, um padrão que define como elas são passadas entre servidores e entre servidores e leitores de correio, e como deve
ser interpretado o conteúdo de cabeçalhos de mensagem. O principal protocolo de camada de aplicação para o correio eletrônico é o SMTP (Simple Mail Transfer Protocol) [RFC 5321]. Assim, o SMTP é apenas um pedaço (embora importante) da aplicação de correio eletrônico.



**2) De que modo mensagem instantânea é um híbrido das arquiteturas cliente-servidor e P2P?**

R:Mencionamos que algumas aplicações possuem arquiteturas híbridas, combinando elementos cliente-servidor e P2P. Para muitas aplicações de mensagem instantânea, os servidores costumam rastrear o endereço IP dos usuários, mas as mensagens entre usuários são enviadas diretamente entre os hospedeiros do usuário (sem passar por servidores intermediários).

**3) O que é um socket?**

R:Um socket é a interface entre a camada de aplicação e a de transporte dentro de um hospedeiro.

**4) Para uma sessão de comunicação entre um par de processos, qual processo é o cliente e qual é o servidor?**

R:No contexto de uma sessão de comunicação entre um par de processos, aquele que inicia a comunicação(isto é, o primeiro a contatar o outro no início da sessão) é rotulado de cliente. O que espera ser contatado para iniciar a sessão é o servidor.

**5) De que serviços de transporte uma aplicação precisa?**

R:Transferência confiável de dados, vazão, temporização e segurança.

**6) Explique o modelo de serviço do TCP.**

R:O modelo de serviço TCP inclui um serviço orientado para conexão e um serviço confiável de transferência de dados. Quando uma aplicação solicita o TCP como seu protocolo de transporte, recebe dele ambos os serviços.

**7) Explique o modelo de serviço do UDP.**

R:O UDP é um protocolo de transporte simplificado, leve, com um modelo de serviço minimalista. É um
serviço não orientado para conexão; portanto, não há apresentação antes que os dois processos comecem a se comunicar. O UDP provê um serviço não confiável de transferência de dados — isto é, quando um processo envia uma mensagem para dentro de um socket UDP, o protocolo não oferece garantias de que a mensagem chegará ao processo receptor. Além do mais, mensagens que chegam de fato ao processo receptor podem chegar fora de ordem.

**8) Cite algumas aplicações de rede e descreva qual o protocolo da camada de aplicação ela utiliza?**

| Aplicação                 | Protocolo da camada de aplicação | Protocolo de transporte usado |
| ------------------------- | -------------------------------- | ----------------------------- |
| Correio eletrônico        | SMTP                             | TCP                           |
| Acesso terminal remoto    | TELNET                           | TCP                           |
| WWW                       | HTTP                             | TCP                           |
| Transferência de arquivos | FTP                              | TCP                           |
| Streaming multimídia      | RealNetworks                     | TCP OU UDP                    |
| Telefonia Internet        | VOIP                             | UDP                           |















