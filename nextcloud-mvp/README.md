# Nextcloud MVP cho cong ty

Day la bo MVP de chay thu he thong luu tru va chia se file noi bo bang Nextcloud.

Muc tieu:

- Co mot "Google Drive rieng" cho cong ty.
- Tao tai khoan nhan vien va nhom phong ban.
- Upload, download, chia se file theo quyen.
- Thu nghiem quy trinh truoc khi dua du lieu that len.
- Chuan bi san checklist bao mat va backup.

## Chay thu tren may local

Yeu cau:

- Docker Desktop da cai san.
- May tinh co toi thieu 4 GB RAM trong luc test.

Buoc chay:

```powershell
cd nextcloud-mvp
Copy-Item .env.example .env
docker compose up -d
```

Mo trinh duyet:

```text
http://localhost:8080
```

Tai khoan admin lay tu file `.env`.

## Chay tren VPS/domain that

1. Tro DNS `A record` cua `cloud.tencongty.com` ve IP VPS.
2. Sua `.env`:

```text
NEXTCLOUD_DOMAIN=cloud.tencongty.com
NEXTCLOUD_ADMIN_PASSWORD=mat-khau-manh
MYSQL_PASSWORD=mat-khau-db-manh
MYSQL_ROOT_PASSWORD=mat-khau-root-manh
```

3. Chay:

```powershell
docker compose -f docker-compose.yml -f docker-compose.production.yml up -d
```

Khi dung file production, Caddy se tu xin HTTPS/SSL neu domain da tro dung ve VPS.

## Tai lieu di kem

- `docs/requirements.md`: bai toan va chuc nang MVP.
- `docs/beginner-setup.md`: huong dan cai Docker va chay thu cho nguoi moi.
- `docs/nextcloud-admin-setup.md`: cac buoc tao nhom, tai khoan, thu muc trong Nextcloud.
- `docs/permission-matrix.csv`: ma tran phan quyen mau.
- `docs/mvp-test-plan.md`: kich ban cho nguoi dung thu nghiem.
- `docs/security-backup.md`: checklist an toan du lieu va backup.

## Luu y quan trong

Ban MVP chi nen dung voi du lieu mau hoac du lieu khong nhay cam. Truoc khi dua du lieu cong ty that len, can hoan thanh backup, MFA, HTTPS, chinh sach phan quyen va ke hoach khoi phuc su co.
