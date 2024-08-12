---
title: Workshop sobre Instalação e Uso do ProxMox Node
description: Um guia introdutório completo para aprender a instalar, configurar e utilizar um node ProxMox. Este workshop também aborda casos de uso práticos, como home lab, servidor para pequenas empresas, e clusters de alta disponibilidade, além de uma demonstração ao vivo da instalação de serviços como Pi-hole e Uptime Kuma.
author: kasTul
date: 2024-08-11 10:00:00 +0800
categories: [Virtualização, Workshop]
tags: [ProxMox, virtualização, tutoriais]
pin: true
image: 
    path: /assets/img/workshopProxMox.webp
    alt: A guilda dos magos-ferreiros.
---

## Introdução

Olá a todos, e bem-vindos a este primeiro workshop do kasTul em instalação e uso de um node ProxMox com enfoque em soberania digital e otimização de recursos computacionais. RECEBA este guia sobre poderosa plataforma de virtualização que pode ajudá-los a gerenciar e implementar máquinas virtuais e contêineres com facilidade.

Vamos começar passando pelo processo de instalação passo a passo e, em seguida, explorar alguns casos de uso práticos onde o ProxMox realmente se destaca. Seja para gerenciar um homelab, um ambiente de pequenas empresas ou até mesmo uma configuração mais extrema, o ProxMox é uma ferramenta versátil que pode atender às suas necessidades bitcoinheirescas.

## O que é ProxMox?

Antes de mergulharmos na instalação, vamos falar brevemente sobre o que é o ProxMox. O ProxMox Virtual Environment, ou ProxMox VE, é uma plataforma de virtualização de código aberto. Ele permite que você gerencie máquinas virtuais, contêineres e até mesmo funções de rede a partir de uma única interface web unificada.

O ProxMox é construído sobre o Debian Linux e usa KVM (Máquina Virtual Baseada em Kernel Virtual Machine) para virtualização completa e LXC (Linux Containers) para virtualização baseada em contêineres.

## Instalação do ProxMox

### Requisitos de Instalação


1. **Requisitos de Hardware:**
   - Processador de 64 bits com suporte a VT-x/AMD-V.
   - Pelo menos 2 GB de RAM (8 GB recomendados).
   - Um disco rígido ou SSD com pelo menos 16 GB de espaço.

2. **Requisitos de Software:**
   - Imagem ISO do ProxMox VE.
   - Um pen drive USB inicializável ou um CD/DVD físico.

3. **Requisitos de Rede:**
   - Uma conexão de rede estável para atualizações e gerenciamento.

### Instalação


1. **Baixe a ISO do ProxMox VE:**
   - Visite o site oficial do ProxMox e baixe a imagem ISO mais recente.

2. **Crie um Pen Drive USB Inicializável:**
   - Use uma ferramenta como Rufus (para Windows) ou `dd` (para Linux) para criar um pen drive USB inicializável a partir da ISO.

3. **Inicialize a partir do USB:**
   - Insira o USB no servidor ou máquina onde você deseja instalar o ProxMox e inicialize a partir do pen drive.

4. **Siga o Assistente de Instalação:**
   - O instalador do ProxMox irá guiá-lo através do processo de instalação, incluindo particionamento de disco, configuração da senha root e configuração inicial de rede (recomendo verificar ANTES qual IP voce vai reservar). Inicialmente eu acho bom selecionar o file system XFS. 

5. **Primeira Inicialização:**
   - Uma vez instalado, o sistema será reiniciado. Você pode acessar a interface web do ProxMox navegando para o endereço IP do servidor em um navegador web (ex.: `https://<ip-do-servidor>:8006`).

6. **Login e Configuração Inicial:**
   - Faça login com a conta root e senha configurada durante a instalação. A partir daqui, você pode começar a configurar o seu node ProxMox.

## Explorando Casos de Uso

### Visão Geral dos Casos de Uso

Agora que temos o ProxMox instalado, vamos dar uma olhada em alguns casos de uso comuns onde o ProxMox pode ser altamente benéfico.

### Caso de Uso 1 - Home Lab

Se você está experimentando diferentes tecnologias ou testando configurações de software, o ProxMox é uma ótima escolha para uma configuração de laboratório doméstico. Você pode criar várias máquinas virtuais (VMs) ou contêineres para simular diversos ambientes.

**Exemplo:** Configurar um ambiente de desenvolvimento com diferentes sistemas operacionais ou testar configurações de rede com roteadores e switches virtuais.

### Caso de Uso 2 - Servidor para Pequenas Empresas

Para pequenas empresas, o ProxMox pode servir como uma robusta plataforma de servidor. Você pode hospedar múltiplos serviços, como um servidor web, servidor de email e armazenamento de arquivos, tudo em uma única máquina física. Além disso, pode-se utilizar ferramentas de orquestração como o Ansible para automatizar e gerenciar a configuração de servidores e contêineres.

**Exemplo:** Implantar um servidor web em uma VM, um servidor de email em outra, e ainda ter espaço para criar VMs ou contêineres adicionais conforme sua empresa cresce. Automatizar tarefas com Ansible para facilitar a manutenção.

### Caso de Uso 3 - Backup e Recuperação de Desastres

O ProxMox oferece funcionalidades integradas de backup e snapshot, tornando-o uma excelente escolha para planos de recuperação de desastres. Você pode agendar backups regulares de suas VMs e restaurá-los rapidamente, se necessário.

**Exemplo:** Fazer backup regularmente de VMs críticas para um local externo ou outro node ProxMox, garantindo um tempo de inatividade mínimo em caso de falha.

### Caso de Uso 4 - Clusters de Alta Disponibilidade e Monitoramento

O ProxMox suporta clustering de alta disponibilidade (HA), permitindo que você conecte múltiplos nodes ProxMox. Isso garante que, se um node falhar, outro pode assumir com mínima interrupção. Além disso, ferramentas de observabilidade e monitoramento, como o Prometheus, Grafana e Uptime Kuma, podem ser instaladas para monitorar o desempenho do cluster e detectar problemas rapidamente.

**Exemplo:** Executar um cluster de servidores web, onde a carga é balanceada entre múltiplas VMs ou contêineres. Se um node falhar, os outros continuam a atender ao tráfego sem interrupções. Monitorar o ambiente usando Uptime Kuma para garantir a disponibilidade dos serviços.

## Demonstração ao Vivo

Agora que cobrimos os fundamentos, vamos mergulhar em uma demonstração ao vivo. Vou mostrar como:

1. **Instalar o Pi-hole usando o Script do tteck:**
   - Passar pelo processo de instalação do Pi-hole em um contêiner LXC utilizando o script do tteck disponível em [https://tteck.github.io/Proxmox/](https://tteck.github.io/Proxmox/).

2. **Instalar o Uptime Kuma:**
   - Demonstrar como configurar o Uptime Kuma em uma VM ou contêiner para observar a disponibilidade de serviços.

## Perguntas e Respostas e Conclusão

Muito obrigado pela atenção! Agora, gostaria de abrir o espaço para perguntas que vocês possam ter. Seja sobre o processo de instalação, casos de uso específicos, ou qualquer outra coisa relacionada ao ProxMox, estou aqui para ajudar.

## Conclusão

Em conclusão, o ProxMox é uma ferramenta poderosa e flexível que pode atender a uma ampla gama de necessidades, desde laboratórios domésticos até infraestruturas críticas de negócios. Espero que este workshop tenha fornecido uma base sólida para começar a usar o ProxMox em seu próprio ambiente.

Obrigado mais uma vez por participar deste workshop, e estou ansioso para ver como vocês aplicarão o ProxMox em seus projetos!

## Informações de Contato

Se tiverem mais perguntas ou precisarem de mais assistência, sintam-se à vontade para entrar em contato comigo em [Suas Informações de Contato]. Boas virtualizações!
