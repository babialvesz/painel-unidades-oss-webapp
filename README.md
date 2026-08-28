# 🏥 Painel de Unidades OSS

Aplicação web que consolida dados operacionais de dezenas de unidades de 
saúde geridas por Organizações Sociais (OSS) — antes espalhados em 
múltiplas planilhas de trabalho — em um portal único, com busca global, 
perfil detalhado por unidade e mapa interativo.

## 🎯 Problema que Resolve

Informações de TIC, leitos, pareceres técnicos, produção, contratos e 
especialidades de cada unidade viviam em planilhas de trabalho separadas, 
sem um ponto único de consulta. Cruzar esses dados manualmente para 
entender o panorama de uma unidade específica era lento e propenso a erro.

## ⚙️ Como Funciona

1. **Camada de dados:** um backend Express busca e cacheia dados de 
   múltiplas abas de planilha (unidades, OSS, TIC, leitos, pareceres, 
   produção, análise de desempenho, metas sugeridas, repasses, 
   especialidades), com um parser de CSV escrito para lidar corretamente 
   com aspas e quebras de linha dentro de células
2. **Autenticação:** login via Google OAuth (Firebase Auth), restrito a 
   contas institucionais e uma lista de e-mails autorizados
3. **Portal de busca:** busca global entre unidades, com perfil detalhado 
   por unidade reunindo todos os indicadores relevantes
4. **Mapa interativo:** visualização geográfica das unidades de saúde 
   (Leaflet), com clustering de marcadores
5. **IA integrada:** uso da API Gemini para funcionalidades de análise 
   dentro da aplicação

## 🛠️ Stack

| Camada | Tecnologia |
|---|---|
| Frontend | React 19 + TypeScript + Vite |
| Estilo | Tailwind CSS |
| Backend | Node.js + Express |
| Autenticação | Firebase Auth (Google OAuth) |
| Mapa | Leaflet + Leaflet MarkerCluster |
| IA | Google Gemini API |
| Fonte de dados | Google Sheets (múltiplas abas, via export CSV) |

## ✨ Funcionalidades

- ✅ Consolidação de 10 fontes de dados diferentes em uma única API interna
- ✅ Cache de dados para evitar sobrecarga na fonte original
- ✅ Autenticação restrita por domínio institucional e lista de e-mails
- ✅ Busca global entre unidades
- ✅ Perfil detalhado por unidade (TIC, leitos, produção, contratos, especialidades)
- ✅ Mapa interativo com clustering
- ✅ Parser de CSV robusto (lida com aspas e quebras de linha em células)

## 🔐 Sanitização

Esta é uma versão pública sanitizada da aplicação real:
- ID real da planilha de origem substituído por placeholder
- Configuração real do Firebase (chaves, IDs de projeto) substituída por placeholders
- E-mails pessoais reais da lista de autorização substituídos por exemplos genéricos
- Nenhuma credencial de API está incluída (uso de variáveis de ambiente)

## 🚀 Como Rodar Localmente

```bash
git clone https://github.com/babialvesz/painel-unidades-oss-webapp.git
cd painel-unidades-oss-webapp
npm install

# Configure o .env com suas próprias credenciais (veja .env.example)
cp .env.example .env

# Configure também o firebase-applet-config.json com um projeto Firebase próprio

npm run dev
```

## 👤 Autora

Desenvolvido por [Bárbara Alves](https://github.com/babialvesz), 
Analista de BI e Dados na SES-PE, com desenvolvimento assistido por IA 
generativa (Google AI Studio).
