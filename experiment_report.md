# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600370
**Name:** Hoang Duc Hung
**Date:** 15/04/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Based on my data, the best choice is Laptop at $1200. | | |
| Garbage Data (`garbage_data.csv`) | Based on my data, the best choice is Nuclear Reactor at $999999. | | |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent tra loi sai vi no dua hoan toan vao du lieu dau vao va dang ap dung logic chon
san pham thuoc nhom `electronics` co `price` cao nhat. Trong `garbage_data.csv`,
ban ghi `Nuclear Reactor` co gia 999999 la mot outlier cuc lon nen da danh lua agent,
khien no dua ra dap an vo ly nhung van rat tu tin. Ngoai ra, duplicate IDs lam giam
tinh nhat quan cua du lieu vi cung mot ID co the dai dien cho nhieu san pham khac
nhau. Wrong data type nhu `ten dollars` o cot `price` co the gay loi hoac lam sai
cac phep so sanh, sap xep. Null values va gia tri 0 cho thay du lieu thieu hoac khong
hop le. Khi nhieu loi data quality xuat hien cung luc, agent se de bi "poisoned" va
tra loi sai lech so voi thuc te.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** (Dong y hay khong? Giai thich ngan gon.)

Dong y. Trong bai thi nghiem nay, prompt khong doi nhung khi thay doi chat luong du
lieu thi cau tra loi cua agent thay doi hoan toan. Bo du lieu sach giup agent chon
dung san pham hop ly, trong khi bo du lieu rac dan no toi mot dap an sai nghiem
trong. Prompt tot rat quan trong, nhung neu data dau vao kem chat luong thi agent van
co the suy luan sai. Vi vay, quality data la nen tang quan trong hon quality prompt.
