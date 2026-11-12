# Laboratórios de Cibersegurança

Laboratórios práticos que realizei na área de cibersegurança.

## Lab 1: Criação e inicialização de uma máquina virtual (VirtualBox)

Criei e iniciei uma máquina virtual Windows 10 no Oracle VM VirtualBox.

- Criei a VM a partir de uma imagem ISO do Windows 10, com instalação desacompanhada.
- Configurei os recursos de hardware: memória RAM e processadores virtuais.
- Iniciei a VM e testei os modos de visualização (ecrã completo e escalado).
- Gravei o processo com o OBS Studio.

**Competências:** virtualização, configuração de ambientes de teste, instalação de sistemas operativos.

[Ver vídeo](https://youtu.be/QcVx4hgljRM) 
---

## Lab 2: Regras de entrada e saída na Firewall do Windows Defender

Configurei regras de entrada e saída na Firewall do Windows Defender com Segurança Avançada, numa máquina virtual Windows (Oracle VM VirtualBox).

- Criei regras de porta TCP/UDP (80, 443, 21 e 53) para permitir ou bloquear ligações.
- Defini condições de segurança: permitir apenas ligações seguras e restringir a utilizadores ou grupos autorizados.
- Dei nomes descritivos a cada regra (por exemplo, "entrada porta 80", "entrada porta 443", "saída UDP porta 53") para facilitar a gestão do tráfego.

**Competências:** Windows Defender Firewall com Segurança Avançada, filtragem de tráfego, portas e protocolos, controlo de acesso.

[Ver vídeo](https://youtu.be/y-B-dYE6NIk)

---

## Lab 3: Criação e instalação de uma máquina virtual Ubuntu (VirtualBox)

Criei e instalei uma máquina virtual com Ubuntu 20.04 no Oracle VM VirtualBox, num computador com Windows.

- Criei a VM a partir da imagem ISO do Ubuntu 20.04.6 Desktop (amd64).
- Configurei a instalação automática (utilizador, palavra-passe e nome da máquina).
- Defini os recursos de hardware: 2048 MB de memória RAM, 1 CPU e 25 GB de disco.
- Arranquei a VM, ajustei o modo de visualização (escalado) e acompanhei a instalação do sistema (verificação de disco e cópia de ficheiros).

**Competências:** virtualização, instalação e configuração de Linux (Ubuntu), dimensionamento de recursos de uma VM.

[Ver vídeo](https://youtu.be/-iDncB4XcHI)
---

## Lab 4: Configuração da firewall do Ubuntu com UFW

Configurei a firewall de uma máquina virtual Ubuntu (VirtualBox) através da linha de comandos, usando o UFW (Uncomplicated Firewall).

- Repus a firewall com `sudo ufw reset`, para partir de um estado limpo.
- Criei regras com `sudo ufw allow` para os serviços necessários: SSH (22), HTTP (80), HTTPS (443), DNS (53), NTP (123), SMTP submission (587) e uma porta personalizada (2222).
- Ativei a firewall com `sudo ufw enable`.
- Verifiquei as regras ativas com `sudo ufw status verbose`.

**Competências:** Linux (Ubuntu), linha de comandos, UFW, filtragem de tráfego, portas e protocolos.

[Ver vídeo](https://youtu.be/dnSChvaqhBA)
---

## Lab 5: Firewall UFW com política "negar tudo por defeito"

Configurei a firewall de uma máquina virtual Ubuntu (VirtualBox) pela linha de comandos, aplicando o princípio do menor privilégio: bloquear todo o tráfego por defeito e permitir apenas o necessário.

- Repus a firewall com `sudo ufw reset`.
- Defini as políticas por defeito para bloquear todo o tráfego de entrada e de saída (`sudo ufw default deny incoming` e `sudo ufw default deny outgoing`).
- Abri apenas os serviços necessários com `sudo ufw allow`: SSH (22), HTTP (80), HTTPS (443), DNS (53), NTP (123), SMTP submission (587) e uma porta personalizada (2222).
- Ativei a firewall com `sudo ufw enable`.
- Verifiquei as regras ativas com `sudo ufw status verbose`.

**Competências:** Linux (Ubuntu), linha de comandos, UFW, política de negação por defeito, princípio do menor privilégio, filtragem de tráfego.

[Ver vídeo](https://youtu.be/m3kTQLD_-K4)
---

## Lab 6: Teste de conectividade entre duas máquinas virtuais (Kali Linux e Windows 10)

Testei a comunicação de rede entre duas máquinas virtuais no Oracle VM VirtualBox: uma com Kali Linux e outra com Windows 10.

- No Kali Linux, consultei a configuração de rede com `ip a` e testei a conectividade com `ping`.
- No Windows 10, verifiquei o endereço IP atribuído com `ipconfig` na Linha de Comandos.
- Realizei testes de ping entre as duas máquinas para validar a comunicação.
- Desativei temporariamente o Firewall do Windows Defender (redes privadas e públicas) para analisar o efeito nos testes de ping, num ambiente de laboratório isolado.
- Voltei ao Kali Linux para repetir os testes de ping.

**Competências:** redes, endereçamento IP, `ping`, `ipconfig`, Kali Linux, Windows, firewall, ambientes virtualizados.

[Ver vídeo](https://youtu.be/C8cd4pwnwy4)
---

## Lab 7: Simulação de teste de intrusão (payload, reverse shell e Meterpreter)

> Laboratório realizado num ambiente totalmente isolado e controlado (duas máquinas virtuais em rede local, sem ligação à internet nem a sistemas de terceiros), apenas para fins de aprendizagem.

Simulei um teste de intrusão entre duas máquinas virtuais no VirtualBox (Kali Linux como atacante, Windows 10 como alvo), usando Metasploit.

- Verifiquei a conectividade entre as VMs com `ping` e confirmei os endereços IP de ambas.
- Gerei um payload executável para Windows com `msfvenom` (meterpreter, reverse TCP).
- Alojei o ficheiro num servidor HTTP simples no Kali Linux e descarreguei-o na VM Windows.
- Configurei um listener no Metasploit (`exploit/multi/handler`) com o payload, IP e porta correspondentes.
- Ao executar o ficheiro na VM Windows, estabeleci uma sessão Meterpreter com sucesso.
- Realizei reconhecimento pós-exploração com `sysinfo` e `getuid`.

**Competências:** Metasploit Framework, msfvenom, reverse shell, Meterpreter, pós-exploração, redes e comunicação cliente-servidor.

[Ver vídeo](https://youtu.be/B_n5NOcvuUg)
---

## Trabalho Final: Exercício de Reconhecimento OSINT

Realizei um exercício de reconhecimento passivo (OSINT), no âmbito do curso de Cibersegurança, sobre uma organização real, usando exclusivamente fontes abertas e ferramentas autorizadas (Netcraft, Censys, MaxMind, Google, Maltego), sem qualquer interação direta com os sistemas da organização.

- Mapeei a infraestrutura pública (IPs, hosting, DNS, subdomínios).
- Identifiquei a superfície de exposição pública (serviços, emails institucionais, documentos indexados).
- Elaborei um relatório com conclusões e recomendações de mitigação.

Por conter informação sobre uma organização real, o relatório completo não é publicado aqui. Posso partilhar os detalhes e a metodologia em entrevista.

**Competências:** OSINT, Netcraft, Censys, Maltego, análise de superfície de ataque, reporting.
