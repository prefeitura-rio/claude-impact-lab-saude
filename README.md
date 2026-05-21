# Claude Impact Lab 2026 | Dataset Saúde do Rio

> *Disclaimer*: todos os dados do desafio passaram por processo de anonimização. Para conhecer mais sobre o processo, veja no final do arquivo

## Acesso Rápido

|Tabela|Descrição|Link do Dado Anonimizado|
|--|--|--|
|Cadastros|Os cadastros de milhares de pacientes|Em breve|
|Consultas Agendadas (Reguladas)|As marcações de consultas, que foram reguladas no municipio|Em breve|
|Atendimentos de Urgência, Emergência e Hospitais|As idas em unidades de urgência, emergência e hospitais|Em breve|
|Visitas dos ACS|O histórico de visitas dos ACS|Em breve|

### Material de Apoio

- Manual do ACS: Link em breve
- Fichas dos ACS: Link em breve

## O problema

### A jornada dos Agentes Comunitários de Saúde

* O Rio possui 6.200 Agentes Comunitários de Saúde (ACS) responsáveis por visitar ativamente 4,5 milhões de residentes.
* Essas visitas ocorrem principalmente nos territórios mais vulneráveis da cidade.
* Hoje, o planejamento das visitas diárias ainda depende muito de:
    * memória dos agentes;
    * papel;
    * conhecimento informal do território.
* Ao mesmo tempo, dados clínicos e sociais relevantes permanecem dispersos e pouco utilizados nos sistemas de atenção primária.
* O desafio é transformar esses dados em uma resposta prática e única a cada manhã:
    * quem visitar;
    * em qual ordem;
    * por qual motivo;
    * com base em risco real e lacunas de cuidado.

### O que acontece se resolvermos

* A presença diária no território passa a ser mais direcionada.
* O cuidado se torna mais preventivo e menos reativo.
* Famílias de alto risco são alcançadas mais rapidamente.
* Condições detectáveis podem ser identificadas mais cedo.
* Emergências e hospitalizações evitáveis tendem a diminuir na cidade.

### Quem se beneficia da solução

* Diretamente:
    * os 6.200 ACS, com uma jornada de trabalho mais clara, segura e priorizada;
    * os 4,5 milhões de residentes acompanhados, que passam a ser vistos mais cedo e com maior frequência quando necessário.
* Indiretamente:
    * equipes das clínicas, que recebem casos melhor priorizados;
    * o sistema municipal de saúde, que pode reduzir emergências evitáveis.

### Como se parece o sucesso

* Todo ACS começa o dia com uma lista confiável de visitas baseada em risco.
* A lista é criada pela solução desenvolvida pelos participantes do Impact Lab.
* Famílias de alto risco são alcançadas em dias, não em semanas.
* Agentes e equipes clínicas permanecem sincronizados em tempo real.
* A cidade passa a registrar:
    * mais famílias visitadas por turno;
    * menos emergências evitáveis.


## Processo de Anonimização

Os dados são anonimizados, somando uma série de técnicas para robustez e segurança dos dados.

1. Hash Criptográfico (SHA256) - Geração de Chave artificial para integração de tabelas. Criação a partir de hash SHA256 com hash secret.
3. Date Shifting - Deslocamento aleatório de dias nas datas de eventos, variando de paciente em paciente, mas mantendo ordem sequancial de eventos.
4. Ruído Geográfico - Adição de até 100m de ruído aleatório nas coordenadas
5. Randomização de Endereços - Embaralhamento de endereços, mas mantendo lógica territorial de equipe.
6. Generalização de Campos - Faixas etárias, categorias de raça/cor, agregação temporal
7. Supressão de Registros - Remoção de procedimentos raros (<1000 ocorrências) e registros com k-anonymity abaixo de 5.