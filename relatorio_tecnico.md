# Relatório Técnico das Execuções

## 1. Introdução
Este relatório apresenta as execuções das atividades realizadas no projeto de sincronização de threads em Java.  
O objetivo é analisar o comportamento dos programas, observando como a presença ou ausência de sincronização afeta a integridade dos dados e a ordem de execução.

---

## 2. Atividades e Execuções

### 2.1 Atividade 1: `MeuDadoMonitorJava`
**Detalhes da execução:**  
- Arquivo executado: `monitor/MeuDadoEventJava.java`  
- Saídas observadas:
```
Armazenar Iniciando...
Armazenar Finalizando...
Carregar Iniciando...
Carregar Finalizando...
Consumidor usando Monitor: 0
Produtor usando Monitor: 0
Armazenar Iniciando...
Armazenar Finalizando...
Produtor usando Monitor: 1
Carregar Iniciando...
Carregar Finalizando...
Consumidor usando Monitor: 1
Armazenar Iniciando...
Armazenar Finalizando...
Produtor usando Monitor: 2
Carregar Iniciando...
Carregar Finalizando...
Consumidor usando Monitor: 2
Armazenar Iniciando...
Armazenar Finalizando...
Produtor usando Monitor: 3
Carregar Iniciando...
Carregar Finalizando...
Consumidor usando Monitor: 3
Armazenar Iniciando...
Armazenar Finalizando...
Produtor usando Monitor: 4
```

**Análise técnica:**  
- O uso do monitor garante acesso ordenado à região crítica entre produtor e consumidor.  
- Cada dado produzido é consumido exatamente uma vez, sem repetições ou leituras incorretas.  
- O fluxo segue um padrão previsível: produção → consumo, mantendo a integridade dos dados.

**Opinião pessoal:**  
- O programa demonstra como a sincronização pelo monitor previne condições de corrida de forma eficaz.  
- A execução é totalmente previsível e consistente, reforçando a importância da sincronização.

---

### 2.2 Atividade 2: `MeuDadoThreadsJava 1 e 2`
**Detalhes da execução:**  
- Arquivos executados: `(MeuDadoThreadsJava 1 e 2)`  
- Saídas observadas:  
*(resumo já fornecido anteriormente)*

**Análise técnica:**  
- Sem sincronização completa, algumas leituras se repetem (`Consumidor: 2`, `Consumidor: 5`), indicando pequenas inconsistências.  
- A produção segue sequência crescente, mas o consumidor pode acessar o mesmo valor mais de uma vez.

**Opinião pessoal:**  
- Demonstra a importância da sincronização. Sem ela, o comportamento torna-se imprevisível, embora os dados ainda sejam produzidos.

---

### 2.3 Atividade 3: `MeuDadoEventJava`
**Detalhes da execução:**  
- Arquivo executado: `eventos/MeuDadoEventJava.java`  
- Saídas observadas:
```
Consumidor usando Eventos: 0
Produtor usando Eventos: 0
Produtor usando Eventos: 1
Consumidor usando Eventos: 1
Produtor usando Eventos: 2
Consumidor usando Eventos: 2
Consumidor usando Eventos: 3
Produtor usando Eventos: 3
Consumidor usando Eventos: 4
Produtor usando Eventos: 4
Consumidor usando Eventos: 5
Produtor usando Eventos: 5
Produtor usando Eventos: 6
Consumidor usando Eventos: 6
Produtor usando Eventos: 7
Consumidor usando Eventos: 7
Produtor usando Eventos: 8
Consumidor usando Eventos: 8
Produtor usando Eventos: 9
Consumidor usando Eventos: 9
Produtor usando Eventos: 10
Produtor usando Eventos: 11
Consumidor usando Eventos: 10
Consumidor usando Eventos: 11
Produtor usando Eventos: 12
Consumidor usando Eventos: 12
Produtor usando Eventos: 13
Consumidor usando Eventos: 13
Produtor usando Eventos: 14
Consumidor usando Eventos: 14
Produtor usando Eventos: 15
Consumidor usando Eventos: 15
Produtor usando Eventos: 16
Consumidor usando Eventos: 16
Produtor usando Eventos: 17
Consumidor usando Eventos: 17
Produtor usando Eventos: 18
Consumidor usando Eventos: 18
Produtor usando Eventos: 19
Consumidor usando Eventos: 19
Produtor usando Eventos: 20
Consumidor usando Eventos: 20
Produtor usando Eventos: 21
Consumidor usando Eventos: 21
Produtor usando Eventos: 22
Consumidor usando Eventos: 22
Produtor usando Eventos: 23
Consumidor usando Eventos: 23
Produtor usando Eventos: 24
Consumidor usando Eventos: 24
Produtor usando Eventos: 25
Consumidor usando Eventos: 25
Produtor usando Eventos: 26
Consumidor usando Eventos: 26
Produtor usando Eventos: 27
Consumidor usando Eventos: 27
Produtor usando Eventos: 28
Consumidor usando Eventos: 28
Produtor usando Eventos: 29
Consumidor usando Eventos: 29
```

**Análise técnica:**  
- A sincronização usando eventos garante que cada dado produzido seja consumido corretamente.  
- Embora haja pequenas alternâncias de ordem entre produtor e consumidor, não há perda ou repetição de dados.  
- O fluxo permanece consistente, demonstrando que eventos funcionam como um mecanismo eficiente de controle entre threads.

**Opinião pessoal:**  
- A execução mostra claramente como a sincronização via eventos mantém a integridade dos dados.  
- Comparado às threads sem sincronização, o comportamento é mais previsível, mas com maior flexibilidade que o monitor.

---

## 3. Conclusão
- Mecanismos de sincronização, como monitores ou eventos, são essenciais para a integridade e previsibilidade em programas multithreaded.  
- Threads sem sincronização apresentam leituras repetidas e resultados inconsistentes.  
- Monitores garantem execução estritamente ordenada, enquanto eventos permitem maior flexibilidade mantendo a integridade dos dados.  
- A prática reforça a importância de escolher o mecanismo de sincronização adequado ao cenário.

---

## 4. Referências
- [Documentação Java sobre Threads e Monitores](https://docs.oracle.com/javase/tutorial/essential/concurrency/)  
- [GitHub Markdown Guide](https://docs.github.com/pt/get-started/writing-on-github/get-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

