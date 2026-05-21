# Claude Impact Lab 2026 | Dataset Saúde do Rio

> *Disclaimer*: todos os dados do desafio passaram por processo de anonimização, com tecnicas de aleatorização, generalização e supressão. Dessa forma, indicadores gerados a partir dos dados não representam a realidade. Os dados apenas ilustram as dinâmicas. Para conhecer mais sobre o processo, veja no final do arquivo.

## Acesso Rápido

|Tabela|Descrição|Link do Dado Anonimizado (Formato PARQUET)|
|--|--|--|
|Cadastros|Os cadastros de milhares de pacientes|https://drive.google.com/file/d/1xqUFT-xn1RUYe8k68DK93Dp5AXXYLIp0/view?usp=drive_link|
|Consultas Agendadas (Reguladas)|As marcações de consultas, que foram reguladas no municipio|https://drive.google.com/file/d/1uhtL47LNV94R8E-G7MHCXmTBQwgi74Z0/view?usp=drive_link|
|Atendimentos de Urgência, Emergência e Hospitais|As idas em unidades de urgência, emergência e hospitais|https://drive.google.com/file/d/1fwVamtyoWE5bpfNZ5pH2Db_TRrtgnwrp/view?usp=drive_link|
|Visitas dos ACS|O histórico de visitas dos ACS|https://drive.google.com/file/d/1xqtVMZPQl9418oKfSrTzm0PmqbV2zHcX/view?usp=drive_link|
|Profissionais ACS|A vinculação dos ACS em termos de equipe e unidade|https://drive.google.com/file/d/1FTk_llakSQMp_sjQMBVrsYyJFbaGszpw/view?usp=drive_link|

### Outros Material de Apoio

- Manuais do ACS: 
    - Manual do ACS (Ministério da Saúde): http://189.28.128.100/dab/docs/publicacoes/geral/manual_acs.pdf
    - Guia Prático do ACS (Ministério da Saúde): http://189.28.128.100/dab/docs/publicacoes/geral/guia_acs.pdf
- Fichas dos ACS: Link em breve
- Principal Repositório de Materiais do Município: https://bibliotecasus.subpav.org/
- Alguns exemplos:
  - https://subpav.org/aps/uploads/publico/repositorio/SMS_ViolenciasPapelACS_A5_v2.pdf
  - https://subpav.org/aps/uploads/publico/repositorio/cartilha-do-agente-comunitario-2014.pdf
  - https://subpav.org/aps/uploads/publico/repositorio/Livro_EnfrentamentoCancerColoUteroMama_PDFDigital_20221101_(2).pdf
  - Etc

## Inteligência no Território — Otimizando o Planejamento de Visitas Domiciliares dos Agentes Comunitários de Saúde

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

Os dados são anonimizados, somando uma série de técnicas para robustez e segurança dos dados:

1. Hash Criptográfico (SHA256) - Geração de Chave artificial para integração de tabelas. Criação a partir de hash SHA256 com hash secret.
2. Amostragem Cadastral - representa uma amostragem de 2000 paciente por equipe. Equipes com menos de 2000 pacientes foram suprimidas.
3. Date Shifting - Deslocamento aleatório de dias nas datas de eventos, variando de paciente em paciente, mas mantendo ordem sequancial de eventos.
4. Anonimização Geográfica - Adição de até 100m de ruído aleatório nas coordenadas
5. Randomização de Endereços - Embaralhamento de endereços, mas mantendo lógica territorial de equipe.
6. Generalização e Agregação de Campos - Faixas etárias, categorias de raça/cor, agregação temporal
7. Outras Supressões - Remoção de procedimentos raros (<1000 ocorrências) e registros com k-anonymity abaixo de 5.

### Impactos
- Indicadores gerados a partir dos dados não representam a realidade.
- O mapeamento no dataset de características com a posição do território não representa a realidade. É um mapeamento aleatório. O mapeamento de características com equipe também foi aleatorizado.
- O dia das visitas e procedimentos não representam a realidade, mas a sequência dos fatos.
- Os endereços possuem um ruído de generalização de 100 metros.
- Os dados não representam toda a população, mas uma amostra dela.


# Referências
- [HIPAA Safe Harbor Method](https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/index.html)
- [Differential Privacy](https://en.wikipedia.org/wiki/Differential_privacy)
- [K-Anonymity](https://en.wikipedia.org/wiki/K-anonymity)