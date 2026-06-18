# Thiet lap trong giao dien Nextcloud

Sau khi dang nhap bang tai khoan admin, lam cac buoc sau.

## Tao nhom

Vao menu nguoi dung/admin va tao cac nhom:

- `Ban giam doc`
- `Ke toan`
- `Nhan su`
- `Kinh doanh`
- `Nhan vien`

## Tao tai khoan test

Tao cac tai khoan:

- `giamdoc`
- `ketoan01`
- `nhansu01`
- `sale01`
- `nhanvien01`

Gan tung tai khoan vao dung nhom tuong ung.

## Tao thu muc

Trong app Files, tao cac thu muc:

- `01_Tai_lieu_chung`
- `02_Ban_giam_doc`
- `03_Ke_toan`
- `04_Nhan_su`
- `05_Kinh_doanh`
- `06_Hop_dong_khach_hang`

## Chia se theo nhom

Dung bang `permission-matrix.csv` de cap quyen.

Goi y:

- Thu muc nhay cam chi chia se cho nhom can thiet.
- Thu muc tai lieu chung co the cho toan cong ty xem.
- Quyen sua/xoa chi nen cap cho nguoi chiu trach nhiem.
- Khong bat public link trong giai doan MVP neu chua can.

## Bat MFA

Trong Settings, tim phan bao mat va bat Two-Factor Authentication neu da cai app ho tro. Tai khoan admin nen bat MFA dau tien.

## Kiem tra file da xoa

Xoa mot file mau, vao Deleted files de khoi phuc. Day la bai test quan trong truoc khi cho nguoi dung thu nghiem.
