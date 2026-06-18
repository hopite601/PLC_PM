# Checklist bao mat va backup

## Bao mat bat buoc truoc khi dung du lieu that

- Dung HTTPS voi domain that.
- Doi toan bo mat khau mac dinh trong `.env`.
- Bat MFA/xac thuc 2 lop cho admin va nhan vien.
- Moi nhan vien co tai khoan rieng, khong dung chung tai khoan.
- Admin chi cap quyen theo nhom, khong chia se cong khai neu khong can.
- Tat hoac han che public link cho tai lieu nhay cam.
- Cap nhat image Docker dinh ky.
- Gioi han SSH vao VPS bang key, khong dung password neu co the.
- Bat firewall, chi mo cac cong can thiet: 22, 80, 443.
- Kiem tra nhat ky dang nhap bat thuong.

## Chien luoc backup toi thieu

Dung nguyen tac 3-2-1:

- 3 ban du lieu.
- 2 noi luu khac nhau.
- 1 ban nam ngoai server chinh.

De xuat cho MVP:

- Backup database MariaDB hang ngay.
- Backup volume `nextcloud_data` hang ngay hoac hang tuan.
- Luu backup sang may khac, o cung roi, hoac storage khac.
- Moi thang test khoi phuc 1 lan.

## Lenh backup tham khao

Backup database:

```powershell
docker compose exec db mariadb-dump -u root -p nextcloud > backups/nextcloud-db.sql
```

Backup file data nen thuc hien bang cong cu backup chuyen dung cua VPS, snapshot, hoac rsync sang may khac. Khong nen chi backup database vi file tai lieu nam trong volume `nextcloud_data`.

## Diem can quyet dinh truoc production

- Dung luong du lieu hien tai la bao nhieu GB?
- Moi thang du lieu tang them bao nhieu?
- Can luu backup trong bao lau?
- Ai la nguoi co quyen admin?
- Khi mat server, cong ty chap nhan ngung he thong toi da bao lau?
- Khi mat du lieu, cong ty chap nhan mat toi da du lieu trong bao lau?
