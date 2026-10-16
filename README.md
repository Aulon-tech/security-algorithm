# 🔐 Security Algorithm — Simplified Crypto Lab

A university cryptography project implementing simplified versions of core security algorithms from scratch in Java 17, without relying on external crypto libraries.

---

## 📌 Qëllimi i Projektit

Ky projekt është realizuar si pjesë e lëndës **Siguria e Informacionit** dhe ka për qëllim të demonstrojë funksionimin e brendshëm të algoritmeve kryesore kriptografike:

- **Simplified SHA-1** — version i thjeshtuar i funksionit hash SHA-1
- **Collision & Preimage Attack** — kërkimi i kolizioneve dhe preimage-ve në hash
- **HMAC-Simplified-SHA1** — Message Authentication Code bazuar në SHA-1 të thjeshtuar
- **RSA Factoring Attack** — sulm ndaj RSA duke faktorizuar çelësin publik `n`
- **RSA Digital Signature** — nënshkrim dixhital dhe verifikim duke përdorur SHA-1 të thjeshtuar

Të gjitha algoritmet janë implementuar nga fillimi (from scratch), duke iu qasur teorisë kriptografike në mënyrë praktike.

---

## 🗂️ Struktura e Projektit

```
src/
├── main/java/
│   ├── app/
│   │   └── Main.java                  # Menu kryesore interaktive (console)
│   ├── sha1simplified/
│   │   ├── SimplifiedSHA1.java        # Implementimi i SHA-1 të thjeshtuar
│   │   └── CollisionFinder.java       # Kërkimi i kolizioneve dhe preimage-ve
│   ├── hmac/
│   │   └── HmacSimplifiedSHA1.java    # HMAC duke përdorur SHA-1 të thjeshtuar
│   ├── rsa/
│   │   └── RSAFactorAttack.java       # Sulmi me faktorizim ndaj RSA
│   ├── signature/
│   │   ├── RSASignatureService.java   # Shërbimi i nënshkrimit RSA
│   │   └── SignatureDemo.java         # Demo: nënshkrim + verifikim
│   └── util/
│       ├── HexUtil.java               # Konvertim hex
│       └── Validation.java            # Validim i inputeve
└── test/java/
    ├── hmac/HmacSimplifiedSHA1Test.java
    ├── rsa/RSAFactorAttackTest.java
    ├── sha1simplified/CollisionFinderTest.java
    ├── sha1simplified/SimplifiedSHA1Test.java
    └── signature/RSASignatureServiceTest.java
```

---

## ⚙️ Teknologjitë e Përdorura

| Teknologjia | Versioni |
|-------------|----------|
| Java        | 17       |
| Maven       | 3.x      |
| JUnit Jupiter | 5.10.2 |

---

## 🚀 Si të Ekzekutohet

### Kërkesat paraprake
- Java 17+
- Maven 3.x

### 1. Kompilimi dhe ekzekutimi

```bash
# Klono projektin
git clone https://github.com/Aulon-tech/security-algorithm.git
cd security-algorithm

# Kompilo
mvn compile

# Ekzekuto
mvn exec:java -Dexec.mainClass="app.Main"
```

### 2. Ekzekutimi i testeve

```bash
mvn test
```

---

## 🖥️ Menu Interaktive

Kur ekzekutohet projekti, shfaqet menu interaktive me opsionet:

```
====================================================
 Simplified Crypto Lab - main menu
====================================================
 1. RSA task 2: factor n and find p, q
 2. Simplified SHA-1 hash a message
 3. Find preimage for fixed digest 4BAFE69C (bounded search)
 4. Second preimage: M' != M with H(M')=H(M) (bounded)
 5. HMAC_Simplified_SHA1
 6. RSA digital signature + verification using Simplified SHA-1
 7. Exit
```

---

## 🔬 Përshkrimi i Algoritmeve

### 🔷 Simplified SHA-1
Version i thjeshtuar i SHA-1 që implementon padding, message scheduling dhe compression function me konstantet dhe rrotullimet standarde.

### 🔷 Collision & Preimage Finder
Kërkim i kufizuar (bounded search) për:
- **Preimage**: gjen `M'` ku `H(M') = target`
- **Second Preimage**: gjen `M' ≠ M` ku `H(M') = H(M)`

### 🔷 HMAC-Simplified-SHA1
Implementon HMAC sipas RFC 2104 duke përdorur SHA-1 të thjeshtuar si funksion hash të brendshëm.

### 🔷 RSA Factor Attack
Demonstron dobësinë e RSA kur `n` është i vogël duke faktorizuar `n = p × q` dhe llogaritë çelësin privat `d`.

### 🔷 RSA Digital Signature
- Gjenerimi i çiftit të çelësave RSA
- Nënshkrimi i mesazhit: `S = H(M)^d mod n`
- Verifikimi: `H(M) == S^e mod n`

---

## 👨‍💻 Autori

**Aulon** — Student i Shkencave Kompjuterike  
🔗 [github.com/Aulon-tech](https://github.com/Aulon-tech)

---

## 📄 Licenca

Ky projekt është realizuar për qëllime akademike.
