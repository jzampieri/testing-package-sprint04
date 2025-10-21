# Valoriza — Testes de Automação (Postman/Newman)


## Pré‑requisitos
- Node.js 18+
- Newman: `npm i -g newman`

## Arquivos
- `valoriza.postman_collection.json`
- `valoriza.postman_environment.json`

O ambiente vem pré‑configurado com:
- `base_url` = `http://localhost:8000`
- `email`, `password`, `user_id`, `bank`, `consentId`

> O token de autenticação é salvo automaticamente no env ao rodar o request **01 - Auth Login**.

## Como rodar
```bash
newman run valoriza.postman_collection.json \
  -e valoriza.postman_environment.json \
  --reporters cli,junit \
  --reporter-junit-export newman-report.xml
```

## Casos cobertos
1. Auth • Login obtém token
2. Open Finance • Consent + contas
3. Transações • Ingestão e risco “Médio” (apostas)
4. Alertas • Feed exibe alerta comportamento com CTA
5. Educação • Recomendações personalizadas
6. XAI • Top features SHAP expostas

## Datasets de apoio
Consulte `../../manual/datasets/transactions_betting.json` e `user_profile_u-1001.json`.
