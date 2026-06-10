# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-2A202600617  
**Name:** Nguyen Anh Chuc  
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay agent voi clean data va garbage data:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Du lieu da duoc validate va transform, nen category electronics va price deu hop le. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Du lieu co duplicate ID, wrong type, null value va outlier rat lon lam ket qua bi sai lech. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent tra loi sai khi dung garbage data vi logic cua agent phu thuoc truc tiep vao
du lieu dau vao. Khi file co duplicate ID, agent khong biet record nao la ban ghi
dung de tin cay. Khi cot price co wrong data type nhu "ten dollars", viec so sanh
hoac sap xep gia co the bi loi hoac tao ket qua khong on dinh. Outlier
`Nuclear Reactor` voi gia 999999 la van de lon nhat trong thi nghiem nay, vi agent
chon san pham electronic co gia cao nhat va vi vay de xuat mot san pham vo ly. Null
values va category rong cung lam agent mat ngu canh, khong loc dung nhom san pham.
Ket qua cho thay prompt tot khong the sua hoan toan mot knowledge base kem chat
luong; neu du lieu rac di vao pipeline, cau tra loi cua agent cung de bi rac theo.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Prompt co the huong dan cach tra loi,
nhung chat luong du lieu quyet dinh noi dung ma agent dua ra. Du lieu sach giup
agent tra loi dung va on dinh hon.
