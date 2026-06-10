# Day 10 Lab: Data Pipeline & Data Observability

**Student ID:** AI20K-2A202600617  
**Name:** Nguyen Anh Chuc

---

## Mo ta

Bai lab nay xay dung mot ETL pipeline don gian bang Python. Pipeline doc du lieu tu
`raw_data.json`, kiem tra chat luong du lieu, loai bo record co `price <= 0` hoac
`category` rong, chuan hoa category sang Title Case, tinh `discounted_price`, them
cot `processed_at`, va luu ket qua vao `processed_data.csv`.

Ngoai phan ETL, bai lab cung kiem tra tac dong cua du lieu sach va du lieu rac len
mot agent mo phong trong `agent_simulation.py`.

---

## Cach chay

### Prerequisites

```bash
pip install pandas pytest
```

Neu dung virtual environment co san trong repo:

```powershell
.\.venv\Scripts\activate
```

### Chay ETL Pipeline

```bash
python solution.py
```

Lenh nay tao file `processed_data.csv`.

### Chay Agent Simulation

Tao du lieu rac:

```bash
python generate_garbage.py
```

Chay agent voi clean data va garbage data:

```bash
python -c "from agent_simulation import simulate_agent_response; print(simulate_agent_response('What is the best electronic product?', 'processed_data.csv')); print(simulate_agent_response('What is the best electronic product?', 'garbage_data.csv'))"
```

---

## Ket qua

Pipeline doc 5 records tu `raw_data.json`, giu lai 3 records hop le va loai 2 records
khong hop le. File output gom cac cot `id`, `product`, `price`, `category`,
`discounted_price`, va `processed_at`.

Ket qua stress test cho thay clean data giup agent chon Laptop la san pham electronic
tot nhat, trong khi garbage data lam agent chon Nuclear Reactor vi outlier gia
999999.
