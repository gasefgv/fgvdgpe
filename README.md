# Gestão para a Aprendizagem — Sergipe

Painel de indicadores educacionais georreferenciados por Diretoria Regional de Educação (DRE).

## 📁 Estrutura do Repositório

```
├── docs/
│   ├── index.html           # Página principal (portal)
│   ├── mapa_geral.html      # Mapa interativo por DRE
│   └── assets/
│       ├── logo.png         # Logo do projeto
│       ├── icon-map.png     # Ícone do mapa
│       └── icon-chart.png   # Ícone de gráficos
│
├── data/
│   ├── base_tabelar.csv     # Dados das escolas (indicadores)
│   └── geojs-28-reg.json    # GeoJSON das DREs de Sergipe
│
└── README.md
```

## 🚀 Como Publicar no GitHub Pages

1. **Faça upload dos arquivos** para um repositório no GitHub

2. **Certifique-se** de que a pasta `data/` está na raiz do repositório (mesmo nível de `docs/`)

3. **Ative o GitHub Pages:**
   - Vá em **Settings** → **Pages**
   - Em "Source", selecione **Deploy from a branch**
   - Selecione a branch `main` e a pasta `/docs`
   - Clique em **Save**

4. **Aguarde** alguns minutos e acesse: `https://seu-usuario.github.io/nome-do-repo/`

## 📊 Indicadores Disponíveis

O painel exibe os seguintes indicadores (configuráveis no código):

| Indicador | Tipo | Agregação |
|-----------|------|-----------|
| SAEB 23 Taxa Participação | Percentual | Média |
| SAEB 23 Nota Média PT | Número | Média |
| SAEB 23 Nota Média Mat | Número | Média |
| SAESE 24 Proficiência PT | Número | Média |
| SAESE 24 Proficiência MAT | Número | Média |
| Participação Avaliação Diagnóstica | Percentual | Média |
| Rendimento Médio Língua Portuguesa Avaliação Diagnóstica | Percentual | Média |
| Rendimento Médio Matemática Avaliação Diagnóstica | Percentual | Média |
| Número de Alunos | Número | Soma |
| Participação Avaliação Formativa | Percentual | Média |
| Rendimento LP Avaliação Formativa | Percentual | Média |
| Rendimento MAT Avaliação Formativa | Percentual | Média |

## 🔧 Personalização

### Alterar colunas/indicadores

Edite o array `INDICADORES` no arquivo `docs/mapa_geral.html` (linha ~280):

```javascript
const INDICADORES = [
    { id: 'Nome_Coluna_CSV', nome: 'Nome Exibido', tipo: 'percentual', agregacao: 'media' },
    // ...
];
```

### Alterar paleta de cores

Edite as variáveis CSS no início dos arquivos HTML:

```css
:root {
    --azul-escuro: #0b5fa5;
    --azul-medio: #1e90ff;
    --azul-claro: #4da6ff;
    --azul-pastel: #f1f9ff;
}
```

### Substituir logo

Substitua o arquivo `docs/assets/logo.png` pela imagem desejada (recomendado: 200x60 pixels).

## 📋 Dependências (CDN)

- [Bootstrap 5.3.2](https://getbootstrap.com/)
- [Leaflet 1.9.4](https://leafletjs.com/)
- [D3.js v7](https://d3js.org/)
- [html2canvas 1.4.1](https://html2canvas.hertzen.com/)
- [Google Fonts - Source Sans Pro](https://fonts.google.com/)

## ⚠️ Limitações

- O CSV deve ter menos de ~5MB para carregamento rápido
- Testado em Chrome, Firefox e Edge (versões recentes)
- A exportação PNG pode não funcionar em todos os navegadores (alternativa: Print → Save as PDF)

## 📝 Licença

Desenvolvido para a Secretaria de Estado da Educação de Sergipe em parceria com a FGV.

---

*Última atualização: Dezembro 2025*
