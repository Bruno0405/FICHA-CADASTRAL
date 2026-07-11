# Ficha Cadastral — Formulário Multi-etapas

Formulário web de cadastro de clientes, desenvolvido originalmente para uso interno em uma empresa onde atuo na área de TI, e adaptado aqui como projeto de portfólio.

O sistema foi criado pra resolver um problema real: substituir uma planilha de cadastro manual por um formulário público, validado e responsivo, que qualquer cliente pudesse preencher pelo celular — sem precisar de backend ou banco de dados próprio.

**[Ver demonstração ao vivo](https://bruno0405.github.io/ficha-cadastral/)**

---

## 💡 Sobre o projeto

A empresa recebia cadastros de clientes por telefone ou papel, o que gerava erros de digitação, CPFs/CNPJs inválidos e retrabalho manual. A ideia foi construir um formulário público, hospedado gratuitamente, que:

- Se adapta ao tipo de cliente (Pessoa Física, Pessoa Jurídica ou Produtor Rural), mostrando só os campos relevantes pra cada caso
- Valida os dados **antes** do envio, evitando cadastros incompletos ou com documentos inválidos
- Funciona sem exigir infraestrutura de servidor — só HTML, CSS e JavaScript puro, hospedado no GitHub Pages

## ⚙️ Funcionalidades

- **Fluxo em 3 etapas** com indicador de progresso visual, guiando o usuário do início ao fim
- **Formulário adaptativo por tipo de cliente**: os campos mudam dinamicamente entre Pessoa Física, Pessoa Jurídica e Produtor Rural, incluindo CPF/CNPJ, Inscrição Estadual, regime de ICMS e destino da mercadoria
- **Validação de CPF e CNPJ com dígito verificador real**, usando o algoritmo oficial de módulo 11 — não é só checagem de tamanho de string, valida matematicamente se o número é válido
- **Máscaras de digitação em tempo real** para CPF, CNPJ, telefone e CEP
- **Validação client-side completa** de todos os campos obrigatórios, com mensagens de erro específicas por campo, antes de permitir avançar de etapa
- **Consentimento LGPD** obrigatório, com checkbox e texto explicativo, antes da conclusão do cadastro
- **Bloqueio inteligente da tecla Enter**: intercepta o comportamento padrão do navegador (que tentaria enviar o formulário prematuramente) e redireciona pra validação da etapa atual
- **Envio via Formspree**, sem necessidade de backend próprio — os dados chegam por e-mail formatados e prontos pra uso
- **Tags Open Graph** configuradas, pra que o link do formulário gere uma pré-visualização com título, descrição e imagem quando compartilhado em WhatsApp ou redes sociais
- **Design responsivo**, funcional tanto em desktop quanto em celular

## 🛠️ Tecnologias

- **HTML5** — estrutura semântica do formulário
- **CSS3** — layout com Grid e Flexbox, sem frameworks externos
- **JavaScript (Vanilla)** — toda a lógica de validação, máscaras, navegação entre etapas e algoritmos de CPF/CNPJ implementados do zero, sem bibliotecas
- **Formspree** — processamento e encaminhamento dos envios do formulário por e-mail
- **GitHub Pages** — hospedagem estática e gratuita

## 📌 Decisões técnicas

- **Sem framework**: optei por JavaScript puro para o projeto real de trabalho, priorizando simplicidade de manutenção e zero dependências externas para uma equipe pequena de TI.
- **Sem backend próprio**: como o volume de cadastros era baixo e o orçamento não previa infraestrutura de servidor, o Formspree resolveu o problema de coleta de dados sem necessidade de banco de dados ou API própria.
- **Validação 100% client-side**: os dados são checados antes mesmo de saírem do navegador, reduzindo erros e melhorando a experiência do usuário — embora, em um cenário com backend, essa validação idealmente seria replicada no servidor também.

---

*Este projeto foi adaptado para fins de portfólio, com as informações e identidade visual originais substituídas por conteúdo genérico.*
