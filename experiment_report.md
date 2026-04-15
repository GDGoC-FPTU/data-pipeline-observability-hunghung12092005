# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-2A202600465
**Name:** Dong Manh Hung
**Date:** 2026-04-15

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Du lieu da duoc lam sach, category duoc chuan hoa, khong co record gia am hay category rong nen agent tra loi on dinh. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Agent khong crash nhung bi outlier danh lua, nen chon mot ket qua phi thuc te va kem tin cay. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi dung garbage data, agent khong con lam viec tren mot nguon du lieu nhat quan nua. Duplicate ID lam cho mot khoa dinh danh khong con dang tin cay, dan den viec truy vet hoac tong hop thong tin bi nham lan. Wrong data types, nhu gia tri gia bang chu "ten dollars", co the lam phep loc, so sanh va tinh toan bi loi ngay trong luc chay. Null values o cac cot quan trong nhu `id` hoac `category` lam mat ngu canh va khien agent khong biet record do thuoc nhom nao. Ngoai ra, outlier cuc lon nhu `999999` co the danh lua logic chon san pham "tot nhat", vi agent de hieu nham gia tri cao bat thuong la lua chon phu hop. Tat ca nhung van de nay cho thay neu du lieu dau vao khong duoc kiem tra va lam sach, thi prompt tot den dau cung kho cuu duoc mot he thong tra loi dua tren du lieu sai.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** (Dong y hay khong? Giai thich ngan gon.)

Toi dong y. Prompt tot co the giup agent dien dat ro hon, nhung neu du lieu nguon bi loi thi cau tra loi van de sai hoac vo nghia. Data quality la nen tang, con prompt quality chi phat huy hieu qua khi nen tang du lieu da du sach va dang tin cay.
