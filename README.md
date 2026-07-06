# Projeto 3: Sistema Supervisório TCP/IP (Qt/C++)

Este repositório contém o Projeto 3 da disciplina de Programação Avançada. O objetivo é consolidar os conceitos de Programação Orientada a Objetos utilizando o framework Qt através do desenvolvimento de duas aplicações cliente (Produtor e Consumidor) que comunicam via protocolo TCP/IP.

## Requisitos Implementados

### Módulo Produtor (`QtTcpClientProducer`)
- Conexão TCP: Configuração dinâmica de IP/Porta conectando na porta `1234`.
- Geração Adaptativa: Envio contínuo de dados via comando `set`.
- Controle Dinâmico: Sliders para ajuste em tempo real de limites numéricos (*Min*/*Max*) e taxa de envio (*Timing*).

### Módulo Consumidor (`QtTcpClientConsumer`)
- Descoberta de Ativos: Envio do comando `list` para carregar máquinas ativas em um `QListWidget`.
- Monitoramento Dedicado: Filtro por IP selecionado na interface para aquisição via comando `get`.
- Gráfico de Tempo Real (Classe Plotter): Widget customizado derivado de `QWidget` implementando o evento `paintEvent` para desenhar e autoescalar geometricamente as últimas 30 amostras recebidas da rede.
- Temporização: Slider de *Timing* controlando o intervalo entre as requisições `get`.

---

## Demonstração de Funcionamento

![Execução Integrada](imagem-projeto3/imagempeojeto.png)
Figura 1: Execução simultânea do Servidor TCP, Cliente Produtor enviando pacotes e Cliente Consumidor renderizando o histórico gráfico correspondente.

---

## Como Executar (Guia Rápido)

### 1. Inicializar o Servidor
Execute o arquivo binário do servidor (`QtTcpServer`) fornecido pelo professor para que ele passe a escutar a porta `1234`.

### 2. Executar os Clientes via Qt Creator
Como ambos os projetos utilizam o CMake, o processo de compilação é idêntico para os dois módulos:

1. No Qt Creator, vá em `File > Open File or Project...` e selecione o arquivo `CMakeLists.txt` (faça primeiro na pasta do Produtor e depois repita na pasta do Consumidor).
2. Configure o Kit de Compilação padrão do seu ambiente.
3. Pressione `Ctrl + R` (ou clique no botão verde *Run*) para compilar e iniciar cada aplicação.

### 3. Roteiro de Teste Rápido
1. No Produtor: Digite `127.0.0.1`, clique em *Connect*, depois clique em Put para começar a injetar dados no servidor.
2. No Consumidor: Digite `127.0.0.1`, clique em *Connect*, clique em *Update* para atualizar a lista, selecione o IP na lista e clique em Start. 
3. O gráfico começará a traçar a série temporal instantaneamente.

---
**Desenvolvido por:** [SEU NOME AQUI]  
**Matrícula:** [SUA MATRÍCULA AQUI]  
**Curso:** Engenharia de Computação / UFRN
