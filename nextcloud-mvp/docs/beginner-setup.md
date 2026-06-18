# Huong dan cho nguoi moi

Tai lieu nay danh cho truong hop ban chua tung dung Docker/Nextcloud.

## Buoc 1: Cai Docker Desktop

Tren Windows, can cai Docker Desktop truoc khi chay MVP.

1. Tai Docker Desktop tu trang chinh thuc cua Docker.
2. Cai dat theo mac dinh.
3. Khoi dong lai may neu duoc yeu cau.
4. Mo PowerShell va kiem tra:

```powershell
docker --version
docker compose version
```

Neu hai lenh tren hien phien ban, may da san sang.

## Buoc 2: Tao file cau hinh rieng

Trong thu muc `nextcloud-mvp`, chay:

```powershell
Copy-Item .env.example .env
```

Mo file `.env` va doi mat khau:

```text
NEXTCLOUD_ADMIN_PASSWORD=mat-khau-admin-manh
MYSQL_PASSWORD=mat-khau-db-manh
MYSQL_ROOT_PASSWORD=mat-khau-root-manh
```

## Buoc 3: Chay Nextcloud

```powershell
docker compose up -d
```

Sau do mo:

```text
http://localhost:8080
```

Dang nhap bang:

- User: gia tri `NEXTCLOUD_ADMIN_USER` trong `.env`
- Password: gia tri `NEXTCLOUD_ADMIN_PASSWORD` trong `.env`

## Buoc 4: Dung thu

Hay test bang du lieu gia truoc, vi day moi la ban MVP.

Nen tao cac file mau nhu:

- `hoa-don-mau.pdf`
- `bao-gia-mau.xlsx`
- `hop-dong-mau.docx`
- `quy-dinh-cong-ty.pdf`

Khong dua du lieu cong ty that len truoc khi hoan thanh checklist trong `security-backup.md`.

## Buoc 5: Dung he thong

Khi muon tat:

```powershell
docker compose stop
```

Khi muon chay lai:

```powershell
docker compose up -d
```

Khong dung lenh xoa volume neu chua backup, vi volume dang chua du lieu va database.
