# Ürün Listeleme API (Django REST Framework)

Bu proje, Django REST Framework kullanılarak geliştirilmiş bir basit REST API'dir. API, ürünlerin listesini almayı, yeni ürün eklemeyi, mevcut ürünleri güncellemeyi ve silmeyi sağlar.

## **Proje Özellikleri**
- Ürünleri listeleme.
- Yeni ürün ekleme.
- Mevcut ürünleri güncelleme.
- Ürün silme.

## **Gereksinimler**
Bu projeyi çalıştırmak için aşağıdaki araçlara ihtiyacınız var:
- Python 3.8+ sürümü
- Django 4.x ve üzeri
- Django REST Framework (DRF)

## **Kurulum**
1. **Depoyu klonlayın:**
   ```bash
   git clone https://github.com/kullaniciadi/soraProject.git
   cd soraProject
Virtual Environment oluşturun ve aktif hale getirin:

bash
Kodu kopyala
python -m venv myenv
source myenv/bin/activate  # Windows için: myenv\Scripts\activate
Gerekli paketleri yükleyin:

bash
Kodu kopyala
pip install -r requirements.txt
Veritabanını hazırlayın:

bash
Kodu kopyala
python manage.py makemigrations
python manage.py migrate
Sunucuyu başlatın:

bash
Kodu kopyala
python manage.py runserver
Admin paneli için kullanıcı oluşturun (isteğe bağlı):

bash
Kodu kopyala
python manage.py createsuperuser
API Dokümantasyonu
Base URL
http://127.0.0.1:8000/api/
Endpointler
1. Tüm Ürünleri Listele
URL: /products/
HTTP Yöntemi: GET
Açıklama: Tüm ürünlerin listesini JSON formatında döndürür.
Yanıt:
json
Kodu kopyala
[
    {"id": 1, "name": "T-shirt", "price": 100.0, "created_at": "2025-01-14T12:00:00Z"},
    {"id": 2, "name": "Jeans", "price": 200.0, "created_at": "2025-01-14T13:00:00Z"}
]
2. Yeni Ürün Ekle
URL: /products/
HTTP Yöntemi: POST
Body:
json
Kodu kopyala
{
    "name": "Sneakers",
    "price": 300.0
}
Yanıt:
json
Kodu kopyala
{
    "id": 3,
    "name": "Sneakers",
    "price": 300.0,
    "created_at": "2025-01-14T14:00:00Z"
}
3. Ürün Güncelle
URL: /products/<id>/
HTTP Yöntemi: PUT
Body:
json
Kodu kopyala
{
    "name": "Updated Sneakers",
    "price": 350.0
}
Yanıt:
json
Kodu kopyala
{
    "id": 3,
    "name": "Updated Sneakers",
    "price": 350.0,
    "created_at": "2025-01-14T14:00:00Z"
}
4. Ürün Sil
URL: /products/<id>/
HTTP Yöntemi: DELETE
Yanıt: 204 No Content
Test Yöntemleri
Postman Kullanarak
GET Request:
URL: http://127.0.0.1:8000/api/products/

POST Request:
URL: http://127.0.0.1:8000/api/products/
Body (raw):

json
Kodu kopyala
{
    "name": "Bag",
    "price": 150.0
}
PUT Request:
URL: http://127.0.0.1:8000/api/products/3/
Body (raw):

json
Kodu kopyala
{
    "name": "Updated Bag",
    "price": 180.0
}
DELETE Request:
URL: http://127.0.0.1:8000/api/products/3/

cURL Kullanarak
GET:
bash
Kodu kopyala
curl http://127.0.0.1:8000/api/products/
POST:
bash
Kodu kopyala
curl -X POST -H "Content-Type: application/json" \
-d '{"name":"Bag","price":150.0}' \
http://127.0.0.1:8000/api/products/
Katkı
Herhangi bir sorunuz veya öneriniz varsa email@example.com üzerinden benimle iletişime geçebilirsiniz.
