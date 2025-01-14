# Ürün Listeleme API (Django REST Framework)

Bu proje, Django REST Framework kullanılarak geliştirilmiş bir basit REST API'dir. API, ürünlerin listesini almayı, yeni ürün eklemeyi, mevcut ürünleri güncellemeyi ve silmeyi sağlar.

## **Proje Özellikleri**
- Tüm ürünleri listeleme.
- Yeni ürün ekleme.
- Mevcut ürünleri güncelleme.
- Ürün silme.

---

## **Gereksinimler**
Bu projeyi çalıştırmak için aşağıdaki araçların sisteminizde yüklü olması gerekir:
- **Python 3.8+**
- **Django 4.x ve üzeri**
- **Django REST Framework (DRF)**

---

## **Kurulum Adımları**

### 1. Depoyu Klonlayın
```bash
git clone https://github.com/kullaniciadi/soraProject.git
cd soraProject
```

### 2. Virtual Environment Oluşturun ve Aktif Hale Getirin
```bash
python -m venv myenv
source myenv/bin/activate  # Windows için: myenv\Scripts\activate
```

### 3. Gerekli Paketleri Yükleyin
```bash
pip install -r requirements.txt
```

### 4. Veritabanını Hazırlayın
```bash
python manage.py makemigrations
python manage.py migrate
```

### 5. Sunucuyu Başlatın
```bash
python manage.py runserver
```

### 6. Admin Paneli İçin Süper Kullanıcı Oluşturun (Opsiyonel)
```bash
python manage.py createsuperuser
```

---

## **API Dokümantasyonu**

### **Base URL**
- `http://127.0.0.1:8000/api/`

### **Endpointler**

#### **1. Tüm Ürünleri Listele**
- **URL:** `/products/`
- **HTTP Yöntemi:** `GET`
- **Açıklama:** Tüm ürünlerin listesini JSON formatında döndürür.
- **Yanıt Örneği:**
```json
[
    {"id": 1, "name": "T-shirt", "price": 100.0, "created_at": "2025-01-14T12:00:00Z"},
    {"id": 2, "name": "Jeans", "price": 200.0, "created_at": "2025-01-14T13:00:00Z"}
]
```

#### **2. Yeni Ürün Ekle**
- **URL:** `/products/`
- **HTTP Yöntemi:** `POST`
- **Body:**
```json
{
    "name": "Sneakers",
    "price": 300.0
}
```
- **Yanıt Örneği:**
```json
{
    "id": 3,
    "name": "Sneakers",
    "price": 300.0,
    "created_at": "2025-01-14T14:00:00Z"
}
```

#### **3. Ürün Güncelle**
- **URL:** `/products/<id>/`
- **HTTP Yöntemi:** `PUT`
- **Body:**
```json
{
    "name": "Updated Sneakers",
    "price": 350.0
}
```
- **Yanıt Örneği:**
```json
{
    "id": 3,
    "name": "Updated Sneakers",
    "price": 350.0,
    "created_at": "2025-01-14T14:00:00Z"
}
```

#### **4. Ürün Sil**
- **URL:** `/products/<id>/`
- **HTTP Yöntemi:** `DELETE`
- **Yanıt:** `204 No Content` (Başarılı silme işlemi)

---

## **Test Yöntemleri**

### **Postman ile Test Etme**
1. **GET Request:**  
   - URL: `http://127.0.0.1:8000/api/products/`

2. **POST Request:**  
   - URL: `http://127.0.0.1:8000/api/products/`  
   - Body:
   ```json
   {
       "name": "Bag",
       "price": 150.0
   }
   ```

3. **PUT Request:**  
   - URL: `http://127.0.0.1:8000/api/products/3/`  
   - Body:
   ```json
   {
       "name": "Updated Bag",
       "price": 180.0
   }
   ```

4. **DELETE Request:**  
   - URL: `http://127.0.0.1:8000/api/products/3/`

### **cURL ile Test Etme**
- **GET Request:**
   ```bash
   curl http://127.0.0.1:8000/api/products/
   ```
- **POST Request:**
   ```bash
   curl -X POST -H "Content-Type: application/json" \
   -d '{"name":"Bag","price":150.0}' \
   http://127.0.0.1:8000/api/products/
   ```

---

## **Katkıda Bulunma**
Herhangi bir hata, öneri veya katkınız için lütfen benimle iletişime geçin:  
E-posta: [sabuncumustafasait@gmail.com](mailto:email@example.com)

