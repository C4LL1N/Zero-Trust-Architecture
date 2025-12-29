# Zero-Trust-Architecture-NIST-SP-800-207

## Zero Trust podstawy:
Zero Trust (ZT) to zbiór pomysłów:

- wszystko jest zasobem

- nikt nie jest automatycznie zaufany

- wszystko jest sprawdzane

- dostęp jest minimalny

- bezpieczeństwo działa cały czas

## ZT access:
<img width="874" height="185" alt="zeroTrustAccess" src="https://github.com/user-attachments/assets/5d4dc1ca-2e05-488a-90f3-943000561a73" />

Dostęp jest dawany przez Policy Enforcment Point

## Reguły ZTA:
- **wszystkie dane i systemy komputerowe są traktowane jako zasoby**
- **Wszytskie komunikacje są zabepieczone niezależnie od lokalizacji.**
- **Dostęp jest przyznawany na jedną sesję**
- **Dostęp zależy od dynamicznych zasad (policies)**
- **Żadne urządzenie nie jest automatycznie zaufane i nigdy nie będzie**
- **Uwierzytelnianie i autoryzacja są ciągłe**
- **Firma powinna zbierać i monitorować jak najwięcej informacji stanie urządzania, próbach logowań itd**

## Logical Components of Zero Trust Architecture:

<img width="1020" height="427" alt="LogicalComponentsofZeroTrustAchitecture" src="https://github.com/user-attachments/assets/874645d7-45e3-47a9-90bc-dd1b0e87ea9e" />

1️⃣ Policy Engine (PE) – PE to „mózg”, który decyduje, kto może wejść i zapisuje swoje decyzje.

To komponent podejmujący ostateczną decyzję, czy dany użytkownik/urządzenie może mieć dostęp do zasobu.

Używa:

zasad firmy

danych z zewnętrznych źródeł (np. system CDM, informacje o zagrożeniach)

Decyzja może być:

zezwolenie

odmowa

cofnięcie dostępu

PE współpracuje ściśle z Policy Administrator (PA)

PE zapisuje wszystkie decyzje (co było zaakceptowane, co odrzucone)

---

2️⃣Policy Administrator (PA) – PA to „ręce” systemu, które otwierają lub zamykają drzwi zgodnie z decyzją mózgu (PE).

Odpowiada za utworzenie lub zamknięcie połączenia między użytkownikiem a zasobem.

PA wykonuje decyzję PE:

jeśli dostęp jest przyznany → PA konfiguruje PEP, by umożliwić połączenie

jeśli dostęp jest odrzucony → PA każe PEP zakończyć połączenie

PA i PE mogą być czasami jednym komponentem, ale logicznie są traktowane osobno

PA komunikuje się z PEP poprzez control plane (kanał decyzyjny)

---

3️⃣ Policy Enforcement Point (PEP) – PEP to „ochroniarz przy drzwiach”, który wpuszcza lub blokuje użytkownika według instrukcji PA.
Odpowiada za:

umożliwienie połączenia

monitorowanie połączenia

zakończenie połączenia między użytkownikiem a zasobem

Komunikuje się z PA, aby:

przekazać żądania dostępu

otrzymać aktualizacje zasad

PEP może być:

jednym komponentem

albo podzielony na: klienta (np. agent na laptopie) i zasób (np. bramka przed serwerem)

portalem działającym jako „strażnik” połączeń

---

Dodatkowe źródła danych wspierające PE:

<img width="962" height="1062" alt="dodatkowezrodka" src="https://github.com/user-attachments/assets/d24b7dd1-73e0-4c4f-bb76-86cac502f95f" />


AAA jest prostym i sprawdzonym systemem, ale:

- ufa sieci wewnętrznej

- decyzje są statyczne

- nie chroni przed nowoczesnymi zagrożeniami i lateral movement

Zero Trust jest „lepsze” w nowoczesnym świecie, bo:

- nie ufa nikomu automatycznie

- kontroluje dostęp dynamicznie

- monitoruje zachowania i zagrożenia

- minimalizuje ryzyko przy skradzionych kontach lub urządzeniach
