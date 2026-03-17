# Relatorio

## 1.1 Organização e descrição da telemetria

A telemetria é o conjunto de dados enviados pelos sensores da nave **Aurora Siger** antes do lançamento. Esses dados são analisados para verificar se todos os sistemas estão em condições seguras.

### Temperatura interna e externa
**Temperatura interna**: monitora os sistemas eletrônicos e cabine.

**Temperatura externa**: mede condições ambientais e influência no casco.

Exemplo de organização:

| Parâmetro	| Unidade |	Descrição |
| --- | --- | --- |
| Temperatura interna |	°C |	Temperatura dentro da nave | 
| Temperatura externa	| °C	| Temperatura do ambiente externo | 

### Integridade estrutural

Indica se a estrutura da nave está intacta.

Valores possíveis:
- **1 = íntegra**
- **0 = falha estrutural**

| Parâmetro | Tipo | Descrição |
| --- | --- | --- |
| Integridade estrutural |	Binário (0/1) | 	Verifica danos ou falhas no casco

### Níveis de energia

Mostra o nível de carga dos sistemas de energia.

| Parâmetro	| Unidade | Descrição |
| --- | --- | --- |
| Nível de energia |	%	| Percentual de energia disponível |

### Pressão dos tanques

Indica se os tanques de combustível estão pressurizados adequadamente.

| Parâmetro |	Unidade	| Descrição |
| --- | --- | --- |
| Pressão dos tanques |	bar ou PSI	| Pressão do combustível |

### Status dos módulos críticos

Avalia subsistemas essenciais (exemplo: navegação, propulsão, comunicação).

Valores possíveis:
- **OK**
- **FALHA**

| Módulo | Status |
| --- | --- |
| Navegação |	OK / FALHA |
| Propulsão	| OK / FALHA |
| Comunicação |	OK / FALHA |

## 1.2 Algoritmo de verificação

Exemplo de **faixas seguras** (podem ser ajustadas conforme o exercício):
- Temperatura interna: **18°C – 27°C**
- Temperatura externa: **−20°C – 40°C**
- Integridade estrutural: **1**
- Energia mínima: **80%**
- Pressão dos tanques: **50 – 100 bar**
- Todos os módulos críticos: **OK**

### Pseudocódigo do algoritmo

``` 
INÍCIO

ler temperatura_interna
ler temperatura_externa
ler integridade_estrutural
ler nivel_energia
ler pressao_tanques
ler status_navegacao
ler status_propulsao
ler status_comunicacao

SE (temperatura_interna >= 18 E temperatura_interna <= 27)
E (temperatura_externa >= -20 E temperatura_externa <= 40)
E (integridade_estrutural == 1)
E (nivel_energia >= 80)
E (pressao_tanques >= 50 E pressao_tanques <= 100)
E (status_navegacao == "OK")
E (status_propulsao == "OK")
E (status_comunicacao == "OK")

ENTÃO
    imprimir "PRONTO PARA DECOLAR"

SENÃO
    imprimir "DECOLAGEM ABORTADA"

FIM SE

FIM
```

### Lógica do algoritmo (explicação)

O sistema verifica **cada condição de segurança**:
- Se **qualquer parâmetro estiver fora da faixa segura**, a decolagem é **abortada**.
- Apenas quando **todas as condições são atendidas simultaneamente**, o sistema retorna **PRONTO PARA DECOLAR**.

Essa lógica segue o princípio de fail-safe, comum em sistemas aeroespaciais.