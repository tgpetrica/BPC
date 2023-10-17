## Analiza algoritmilor
- **Corectitudinea**: se analizeaza daca algoritmul produce rezultatul dorit dupa efectuarea unui numar finit de operatii
- **Eficienta**: se estimeaza volumul de resurse (memorie, timp) necesare pentru executia algoritmului

## Verificarea corectitudinii
- **Experimentala (prin testare)**: algoritmul este executat pentru un set de insatnte ale datelor de intrare
- **Formala (prin demonstrare)**: se demonstreaza ca algoritmul produce rezultatul corect pentru orice instante ale datelor de intrare

## Avantaje si dezavantaje
|             |            Experimentala            |                               Formala                              |
|:-----------:|:-----------------------------------:|:------------------------------------------------------------------:|
|   Avantaje  | - simpla  - relativ usor de aplicat |                     - garanteaza corectitudinea                    |
| Dezavantaje |    - nu garanteaza corectitudinea   | - destul de dificila - nu poate fi aplicata algoritmilor complecsi |

## Notiuni de baza
- **Preconditii**: proprietati satisfacute de catre datele de intrare
- **Postconditii**: proprietati satisfacute de catre datele de iesire
- **Verificarea corectitudinii partiale**: se demonstreaza ca daca algoritmul se termina dupa un numar finit de prelucrari atunci conduce de la preconditii la postconditii
- **Verificarea corectitudinii totale**: corectitudine partiala + finititudine
Etape intermediare in verificarea corectitudinii:
- analiza starii algoritmului
- si a efectului pe care il are fiecare pas de prelucare asupra starii algoritmului
### Starea unui algoritm
=  set de valori corespunzatoare variabilelor utilizare in cadrul algoritmului
- de-a lungul executiei algoritmului starea acestuia se modifica intrucat variabilele isi schimba valorile
- algoritmul poate fi considerat corect daca la sfarsitul executiei prelucrarilor starea lui implica postconditiile

*Exemplu:* Rezolvarea ecuatiei ax=b
Preconditii: a ≠ 0
Postconditii: x satisface ax=b

```pseudocode
solve (real a,b)
{
	real x
	x = b/a
	return x
}
```

Apel: `solve(a0,b0)`

### Asertiuni
= afirmatie adevarata privind starea algoritmului
- sunt utilizate pentru a adnota algoritmii
Adnotarea este utila in:
- verificarea corectitudinii algoritmilor
- instrument de documentare si depanare a programelor
*Obs.: ~ comentarii*

```pseudocode
min (real a,b,c) // a≠b, b≠c, c≠a
real m
IF a<b THEN // a<b
	IF a<c THEN m=a // a<b, a<c m=a
		ELSE m=c // a<b, c<a m=c
	ENDIF
ELSE // b<a
	IF b<c THEN m=b // b<a, b<c m=b
		ELSE m=c // b<a, c<b, m=c
	ENDIF
ENDIF
RETURN m
```

```pseudocode
min (real a,b,c) // a≠b, b≠c, c≠a
{
	real m
	m = a // m=a
	IF m > b THEN 
	{
		m = b // m<=a, m<b
	}
	IF m > c THEN
	{
		m = c // m<=a, m<b, m<c
	}
	RETURN m
}
```
## Etapele verificarii corectitudinii
1. Identificam preconditiile si postconditiile
2. adnotarea algoritmului cu asertiuni astfel incat:
- preconditiile sa fie satisfacute
- asertiunea finala sa implice postconditiile
3. **se demonstreaza** ca fiecare pas de prelucrare asigura modifcarea starii algoritmului astfel incat asertiunea urmatoare sa fie adevarata.

### Notatii
- **P** = preconditii
- **Q** = postconditii
- **A** = algoritm
Tripletul (P,A,Q) reprezinta un algoritm corect daca datele de intrare satisfac preconditiile (P), in urma parcurgerii algoritmului (A) sa rezulte postconditiile (Q).

## Reguli pentru verificarea corectitudinii
#### Prelucrari secventiale
Daca
	Preconditiile implica asertiunea initiala
	Fiecare actiune implica asertiunea urmatoare
	Asertiunea finala implica postconditiile
Atunci
	secventa de prelucrari este corecta
#### Prelucrari de decizie
#### Prelucrari repetitive


