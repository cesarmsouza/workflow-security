# Segurança na Pipeline

Este documento descreve as práticas e ferramentas de segurança implementadas nesta pipeline para o projeto Flask RestPlus Server Example.

## Objetivo

O objetivo desta pipeline é garantir a segurança contínua do código e da aplicação por meio da integração de ferramentas de SAST (Static Application Security Testing) e DAST (Dynamic Application Security Testing). As ferramentas escolhidas para essa finalidade são Bandit para SAST e OWASP ZAP para DAST.

## Ferramentas Utilizadas

### Bandit (SAST)

Bandit é uma ferramenta de análise estática de segurança para Python. Ela procura por vulnerabilidades conhecidas e práticas inseguras no código-fonte.

#### Processo de Implementação

1. A pipeline instala as dependências Python necessárias.
2. Executa a análise estática de segurança com Bandit.
3. Os resultados são salvos no arquivo `bandit-results.json`.

### OWASP ZAP (DAST)

OWASP ZAP é uma ferramenta de teste de segurança de aplicativos da web que realiza varreduras dinâmicas em busca de vulnerabilidades.

#### Processo de Implementação

1. A pipeline utiliza o Docker para executar OWASP ZAP.
2. A varredura é realizada na aplicação Flask, assumindo que ela está em execução em http://localhost:5000.
3. Os resultados da varredura são salvos no arquivo `zap-report.html`.

## Como Contribuir

1. Clone o repositório.
2. Faça suas alterações.
3. Envie um pull request.

## Resultados de Segurança

Os resultados das verificações de segurança são armazenados como artefatos da pipeline. Eles podem ser baixados para revisões específicas diretamente no GitHub.

### Bandit Results

Os resultados do Bandit estão disponíveis no arquivo [bandit-results.json](security-results/bandit-results.json).

### OWASP ZAP Results

Os resultados da varredura OWASP ZAP estão disponíveis no arquivo [zap-report.html](security-results/zap-report.html).

## Executando Localmente

Para executar manualmente as verificações de segurança localmente, siga as instruções no arquivo `.github/workflows/security.yml`.

---

**Nota:** Este README detalhado está em um arquivo separado para manter a clareza do README principal. Certifique-se de incluir referências a este arquivo no README principal ou em uma seção de documentação do projeto.
