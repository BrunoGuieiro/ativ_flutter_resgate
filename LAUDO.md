1.  lib/models/ocorrencia.dart
Sintoma: Responsável errado aparecendo
Causa: Pegava autorNome ao invés de autorId
Correção: Troquei para pegar autorId do documento
Teste: Conferi que agora mostra o dono certo

2. lib/models/ocorrencia.dart
Sintoma: Status vindo invertido
Causa: Tinha um ! na hora de ler resolvido
Correção: Tirei o !
Teste: Marcado como resolvido apareceu como resolvido

3. lib/services/central_service.dart
Sintoma: Dono não batia com quem registrou
Causa: Salvei u.email no autorId
Correção: Salvei u.uid
Teste: Só o dono conseguiu mexer no status

4. lib/services/central_service.dart
Sintoma: Ordem errada dos registros
Causa: orderBy com descending false
Correção: Mudei pra descending true
Teste: Mais novo aparece primeiro

5. lib/services/central_service.dart
Sintoma: Não mudava o status
Causa: Atualizava com o mesmo valor
Correção: Passei !item.resolvido
Teste: Consegui marcar e reabrir

6. lib/services/central_service.dart
Sintoma: Pistas indo pro lugar errado
Causa: Pegava doc('pistas') fixo
Correção: Passei ocorrenciaId certo
Teste: Pista apareceu na ocorrência certa

7. lib/pages/central_page.dart
Sintoma: Só registrava se preenchesse os dois
Causa: Usava &&
Correção: Mudei pra ||
Teste: Exigindo os dois agora (se faltar um avisa)

8. lib/pages/central_page.dart
Sintoma: Filtro mostrava errado
Causa: Invertia valor e filtrava resolvidos
Correção: Tirei inversão e filtrei !resolvido
Teste: Só não resolvidos aparecem com filtro ligado

9. lib/pages/central_page.dart
Sintoma: Abria detalhe sem dados
Causa: Não passava ocorrencia
Correção: Passei ocorrencia: o
Teste: Detalhe abre com os dados certos

10. lib/pages/detalhe_page.dart
Sintoma: Não conseguia enviar pista
Causa: Condição invertida e enviava vazio
Correção: Arrumei condição e envio do texto
Teste: Consegui enviar e ver pista

11. lib/pages/detalhe_page.dart
Sintoma: Texto estranho
Causa: Encoding
Correção: Arrumei strings
Teste: Aparece normal

12. lib/pages/central_page.dart
Sintoma: Texto estranho
Causa: Encoding
Correção: Arrumei strings
Teste: Aparece normal
