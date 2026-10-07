# DIO-DESAFIO-2---JobMatch-ATS--
Otimizador de currículos para sistemas ATS. Compara o currículo com a vaga, calcula o match de palavras-chave e gera um PDF A4 amigável e selecionável para robôs de RH. Feito com React, Tailwind e jsPDF.

# 🚀 JobMatch ATS - Otimizador de Currículos para Seleção Automatizada

> Aplicação web desenvolvida no desafio de código Lovable/DIO para comparar currículos com descrições de vagas e gerar uma versão amigável para leitores ATS (Applicant Tracking Systems).

🌐 **Aplicação no Ar:** {https://click-resume.lovable.app}

---

## 📋 Sobre o Projeto
Muitos profissionais qualificados são descartados em etapas preliminares de processos seletivos porque seus currículos não contêm a formatação ou as palavras-chave exatas esperadas pelos robôs de triagem (ATS). 

O **JobMatch ATS** resolve esse problema analisando o texto da vaga, calculando o nível de compatibilidade do currículo atual, mapeando as palavras-chave faltantes e reestruturando o conteúdo em um formato padrão aceito por qualquer ATS.

### 🛑 Ética & Integridade
A aplicação segue estritamente a **Regra de Ouro**: o sistema otimiza a apresentação das experiências reais do candidato, **jamais inventando dados, empresas ou competências não declaradas**.

---

## 🛠️ Tecnologias Utilizadas
- **Desenvolvimento Low-Code / AI-Driven:** [Lovable.dev](https://lovable.dev)
- **Framework Frontend:** React + Vite
- **Estilização:** Tailwind CSS
- **Design System:** `shadcn/ui`
- **Ícones:** Lucide React
- **Exportação:** `html2pdf.js`

---

## 🧠 Evolução do Mega Prompt
O projeto foi iniciado utilizando um Mega Prompt detalhado contendo diretrizes visuais e regras de negócio. Durante o processo de desenvolvimento, os seguintes ajustes foram realizados via chat no Lovable:

1. **Adição da Exportação em PDF:** Solicitação de integração com biblioteca cliente para download imediato do currículo formatado.
2. **Refinamento do Algoritmo de Extração:** Ajuste no prompt do motor de análise para classificar palavras-chave entre *Hard Skills* e *Soft Skills*.
3. **Melhoria da Acessibilidade do Layout:** Ajuste nas tabelas de badges para melhor leitura em dispositivos móveis.

## Mega Prompt Finalizado:

# """ INICIO DO PROMPT """

# Visão Geral do Produto: JobMatch ATS

Crie uma aplicação web moderna, responsiva e acessível focada em otimizar currículos para passar por sistemas ATS (Applicant Tracking Systems). A aplicação compara o currículo do usuário com a descrição de uma vaga de emprego, identifica lacunas de palavras-chave e gera uma versão reestruturada e amigável para ATS.

---

## 🛑 Regra de Ouro da Aplicação
A aplicação DEVE apenas reorganizar, destacar e reescrever as experiências existentes do candidato para alinhar com o vocabulário da vaga. NUNCA invente habilidades, empresas, cargos, certificações ou experiências que não estejam presentes no currículo original. Adicione um aviso visual explícito sobre essa diretriz na interface.

---

## 🎨 Design System & UI
- **Biblioteca de Componentes:** `shadcn/ui` (Cards, Tabs, Buttons, Progress Bars, Badges, Textarea, Tooltips, Dialogs).
- **Ícones:** `lucide-react`.
- **Paleta de Cores (Tema Dark/Light amigável):**
  - **Fundo:** Dark Slate / Dark Zinc (`bg-slate-950` / `text-slate-50`).
  - **Primária (Ação):** Indigo/Violet (`bg-indigo-600` / `hover:bg-indigo-500`).
  - **Sucesso (Match alto/Palavras encontradas):** Emerald (`text-emerald-400`, `bg-emerald-950/50`).
  - **Alerta/Lacuna (Palavras ausentes):** Amber/Rose (`text-rose-400`, `bg-rose-950/50`).
- **Tipografia:** Sans-serif limpa e profissional (Inter ou similar).

---

## 📐 Estrutura de Telas e Layout

### 1. Header (Navegação)
- Logo com ícone (`BriefcaseCheck` ou `FileSearch`) e nome "JobMatch ATS".
- Badge indicativa: "Versão Beta / Otimizador ATS".
- Botão de alternância de tema (Light/Dark mode) e link para documentação/GitHub.

### 2. Hero Section
- Título principal atraente: "Seu currículo nunca mais barrado pelo robô do RH."
- Subtítulo explicativo detalhando o fluxo simples em 3 passos.

### 3. Área Principal de Entrada (Layout de 2 Colunas no Desktop)
- **Coluna 1 - Descrição da Vaga:**
  - Label: "Cole aqui os requisitos da Vaga"
  - Textarea com suporte a placeholders explicativos.
  - Contador de caracteres/palavras.
- **Coluna 2 - Currículo Atual:**
  - Label: "Cole aqui o seu Currículo Atual"
  - Textarea similar ao da vaga.
- **Ação Central:** Botão destacado "Analisar e Otimizar Currículo" com ícone de raio/processamento.

### 4. Painel de Resultados (Exibido após acionar a análise)
- **Card de Score Match:**
  - Marcador circular ou barra de progresso destacada mostrando a porcentagem de pontuação de compatibilidade (0% a 100%).
  - Classificação visual: Baixa (<50%), Média (50-75%), Excelente (>75%).
- **Tabs de Diagnóstico:**
  - **Aba 1: Palavras-chave Encontradas:** Badges verdes com as competências técnicas e soft skills coincidentes.
  - **Aba 2: Palavras-chave Ausentes:** Badges vermelhas/amarelas com termos cruciais presentes na vaga, mas ausentes no currículo.
  - **Aba 3: Sugestões de Melhoria:** Lista estruturada de recomendações de verbos de ação e formatação.
- **Aba 4: Currículo ATS Friendly Otimizado:**
  - Visualização em documento limpo (folha A4 estilizada em Markdown/HTML).
  - Texto reorganizado contendo: Resumo Profissional Alinhado, Seção de Habilidades Destacadas, Experiências Otimizadas com palavras-chave relevantes aplicadas ao contexto real do usuário.
  - **Botões de Ação:** "Copiar Texto" e "Exportar em PDF".

### 5. Ao final, Implemente a biblioteca html2pdf.js ou jspdf / html2canvas para converter a div do currículo otimizado diretamente em um arquivo PDF formatado para download. """"

# """ FIM DO PROMPT """

---

## ⚙️ Lógica & Mock do Algoritmo de Análise
1. Extrair palavras-chave técnicas (Hard Skills), habilidades comportamentais (Soft Skills) e requisitos da vaga.
2. Comparar a frequência e correspondência exata/parcial desses termos com o texto do currículo original.
3. Calcular a pontuação percentual ($Score = \frac{Termos\,Encontrados}{Total\,de\,Termos\,Chave} \times 100$).
4. Gerar a versão ajustada do currículo mantendo 100% da veracidade do conteúdo original, mas reestruturando tópicos e aplicando formatação limpa (sem colunas duplas, sem tabelas complexas ou gráficos incompatíveis com leitores ATS).

---

## 📖 Como Usar a Aplicação
1. Cole a descrição completa da vaga desejada no campo à esquerda.
2. Cole o texto completo do seu currículo atual no campo à direita.
3. Clique em **Analisar e Otimizar Currículo**.
4. Visualize o seu **Score de Match** e analise as palavras-chave encontradas e ausentes.
5. Copie a versão do currículo otimizado ou faça o download em **PDF**.

---

## 📸 Demonstração
<img width="826" height="454" alt="image" src="https://github.com/user-attachments/assets/fa43ecc0-0b3a-4603-9f68-6ca49c8a99a7" />

<img width="604" height="404" alt="image" src="https://github.com/user-attachments/assets/033a767d-db92-4b88-90dc-4732b317ba47" />
