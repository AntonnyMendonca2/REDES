# **Endereçamento IP**

O **IP** é uma forma de uma máquina se identificar na rede, é uma identidade.

## **Servidor DNS** 
É o responsável por traduzir o link de um servidor em um IP, exemplo, quando pingamos o *www.google.com*, na verdade pingamos um IP como *2800:3f0:4001:831::2004*, quem faz essa tradução é o servidor DNS.

## **Ping**

 O **Ping** é feito pelo protocolo **ICMP (Internet Control Message Protocol)**. Uma informação importante sobre o ping é a sigla TTL (time to live), o valor apresentado por essa sigla significa por quantas máquinas (hops) nossa informação pode passar para chegar no destino final, ne **internet**, por exemplo, nosso ping não vai diretamente para a máquina em que o google fica hospedado, e sim por diversas outras que ficam no caminho.

 ## **Tracerout**
 Para ver o *tracerout* da nossa máquina até outro ip, basta usar o comando **tracert** e a url/ip em seguida:

 ![tracerout](./imagens/tracerout.png)

 No caso das máquinas 2,6 e 8 tomamos timeout, isso pode acontecer se o provedor desabilitar a resposta para requisições **ICMP**, isso porque é assim que começam ataques **DDOS**e outros tipos de tentativas de invasão.

 para testar nossa placa de rede com testes internos, ou *loopback*, basta dar um ping em um ip reservado que começa com 127, por exemplo:
 ```CMD
 ping 127.0.0.1
 ```

 O **DNS** padrão da nossa máquina chama nosso IP de Localhost, mas isso pode ser alterado na pasta /hosts lá na C:\Windows\System32\drivers\etc do windows.

 no MAC:

```CMD
sudo vi /private/etc/hosts
```
Linux:
```CMD
sudo vi /etc/hosts
```

**nslookup:** "O Nslookup pode ser usado para descobrirmos o endereço IP de um domínio, bem como saber detalhes mais avançados de DNS, para saber se nosso serviço está sendo direcionado para a máquina de destino, por exemplo."

> Comando para verificar o ip de um domínio, mais ou menos isso.

**Hub:** Equipamento utilizado para conectar vários computadores.

# **Tipos de cabos**

Quando compramos um cabo de internet, geralmente ele vem de um lado com os fios soltos e do outro conectado a um objeto de plástico chamado **RJ45**, o processo de inserir os fios soltos ao **RJ45** chamasse **crimpar**.

## **Tipos de conexões**:

Começando pelo cabo direto:

![conexão direta](./imagens/cabo%20direto.png)
No cabo direto, a conexão é feita com a seguinte sequência de cores:
```
- Branco do verde;
- Verde;
- Branco do laranja;
- Azul;
- Branco do azul;
- Laranja;
- Branco do marrom;
- Marrom.
```

Essa ordem de cores é no padrão **T568A**.

Observe na imagem, os dados saem do computador pelo primeiro e segundo fio e chegam pelo terceiro e sexto fio, já no hub, essa transmissão de dados é feita de forma contrária.

Agora, quando precisamos conectar um computador no outro através de um cabo de rede, o que acontece? bom, como a placa de rede de ambos computadores segue o padrão do **T568A**, quando um computador tentar enviar um dado para o outro nos fios 1 e 2, o outro computador não vai ser capaz de recebe-los, dado que sua placa de rede funciona da mesma forma, usando os fios 1 e 2 somente para envio de dados, é ai que entra um outro padrão de cores, chamado **T568B**, porém , essa sequência de cores é seguida em somente um dos lados do cabo.

a sequencia de cores do **T568B** é a seguinte:
```
- Branco do laranja;
- Laranja;
- Branco do verde;
- Azul;
- Branco do azul;
- Verde;
- Branco do marrom;
- Marrom.
```

Essa conexão chamasse **Crossover**

![cross-over](./imagens/T568A%20-%20T568B.png)

Hoje em dia, algumas placas de rede possuem o padrão auto-MDIX, conseguindo detectar os fios nas posições incorretas, corrigindo isso via software, é por isso que, as vezes, conseguimos conectar dois computadores através de um cabo direto.
