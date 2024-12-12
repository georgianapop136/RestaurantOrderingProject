# Documentație API Backend

## 1. Prezentare generală
Acest API oferă funcționalități backend pentru gestionarea alimentelor, utilizatorilor, coșului de cumpărături și facturilor. Este construit folosind **Express.js** și oferă metode pentru interacțiuni RESTful. Beneficiile includ ușurința de integrare, autentificare sigură și o gamă largă de endpoint-uri pentru diverse operații.

## 2. Instalare

1. Clonează acest repository:
   ```bash
   git clone <URL>
   ```
2. Navighează în directorul proiectului:
   ```bash
   cd <nume-proiect>
   ```
3. Instalează dependențele necesare:
   ```bash
   npm install
   ```
4. Rulează serverul local:
   ```bash
   npm start
   ```

## 4. Endpoint-uri principale

### 4.1. Food (Produse alimentare)
- **GET /api/foods**: Obține lista tuturor alimentelor.
- **GET /api/foods/:id**: Detalii despre un produs alimentar.
- **POST /api/foods**: Creează un nou produs alimentar.
- **PUT /api/foods/:id**: Actualizează un produs alimentar.
- **DELETE /api/foods/:id**: Șterge un produs alimentar.

### 4.2. User (Utilizatori)
- **GET /api/users/:id**: Obține informații despre un utilizator specific.
- **POST /api/users**: Creează un cont de utilizator.

### 4.3. Cart (Coș de cumpărături)
- **POST /api/cart**: Adaugă produse în coș.
- **GET /api/cart/:id**: Obține detalii despre un produs din coș.
- **PUT /api/cart/:id**: Actualizează produsul din coș.
- **GET /api/cart**: Obține toate produsele din coș.
- **DELETE /api/cart/:id**: Șterge un produs din coș.
- **DELETE /api/cart**: Șterge toate produsele din coș.

### 4.4. BillDetails (Detalii facturi)
- **POST /api/billdetails**: Creează detalii pentru o factură.
- **GET /api/billdetails/:id**: Obține detalii despre o factură.

### 4.5. BillStatus (Status facturi)
- **GET /api/billstatus/newest**: Obține cel mai recent status al facturilor.
- **POST /api/billstatus**: Creează un status pentru o factură.
- **GET /api/billstatus/user/:id**: Toate facturile unui utilizator.
- **GET /api/billstatus/:billId**: Detalii despre o factură specifică.
- **GET /api/billstatus**: Toate facturile existente.
- **PUT /api/billstatus/:id**: Actualizează un status.
- **PUT /api/billstatus/paid/:id**: Marchează factura ca plătită.
- **PUT /api/billstatus/cancel/:id**: Anulează o factură.

## 5. Coduri de stare și erori

- **200 OK**: Cererea a fost procesată cu succes.
- **201 Created**: Resursa a fost creată cu succes.
- **400 Bad Request**: Cererea este invalidă.
- **401 Unauthorized**: Lipsa autentificării sau token invalid.
- **404 Not Found**: Resursa nu a fost găsită.
- **500 Internal Server Error**: Eroare pe server.

## 6. Exemple de utilizare

### GET /api/foods
**Cereră:**
```
GET /api/foods HTTP/1.1
Host: example.com
Authorization: Bearer <token>
```
**Răspuns:**
```json
[
  {
    "id": 1,
    "name": "Pizza Margherita",
    "price": 25.5
  },
  {
    "id": 2,
    "name": "Spaghetti Carbonara",
    "price": 30.0
  }
]
```

### POST /api/cart
**Cereră:**
```json
{
  "productId": 1,
  "quantity": 2
}
```
**Răspuns:**
```json
{
  "message": "Produs adăugat în coș."
}
```

## 7. Glosar
- **Endpoint**: URL unde API-ul poate fi accesat pentru o anumită funcționalitate.
- **Token JWT**: Metodă de autentificare care oferă acces securizat la API.
- **Cod de stare**: Mesaj numeric returnat de server pentru a indica succesul sau eșecul unei cereri.

