[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574166&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** hunghung12092005@example.com
**Name:** Dong Manh Hung

---

## Mo ta

Bai lab nay xay dung mot ETL pipeline don gian de doc du lieu JSON, kiem tra chat luong du lieu, chuan hoa du lieu va luu ket qua ra file CSV. Trong bai lam nay, toi da hoan thien day du 4 buoc Extract, Validate, Transform, Load; dong thoi bo sung logging de quan sat so record hop le va record bi loai.

Ngoai pipeline ETL, bai lab con mo phong tac dong cua du lieu sach va du lieu rac den ket qua cua AI agent. Toi da chuan bi bao cao so sanh giua `processed_data.csv` va `garbage_data.csv` de phan tich vi sao chat luong du lieu anh huong truc tiep den do chinh xac cua cau tra loi.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas pytest
```

### Chay ETL Pipeline
```bash
python solution.py
```

Sau khi chay xong, script se tao file `processed_data.csv`.

### Chay Agent Simulation (Stress Test)
```bash
python solution.py
python generate_garbage.py
python agent_simulation.py
```

Quy trinh tren se:
- Tao `processed_data.csv` tu du lieu sach da qua ETL
- Tao `garbage_data.csv` chua cac loi data quality
- Chay agent tren ca hai bo du lieu de so sanh ket qua

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

Pipeline doc tong cong 5 records tu `raw_data.json`. Sau buoc validation, 3 records hop le duoc giu lai va 2 records bi loai bo do loi gia am hoac category rong. Buoc transform da them cot `discounted_price`, chuan hoa `category` sang Title Case va gan them timestamp `processed_at`.

Ket qua cuoi cung duoc luu vao `processed_data.csv`. Khi mo phong agent, bo du lieu sach giup agent tra loi on dinh va hop ly hon, trong khi bo du lieu rac de gay ra ket qua sai lech do duplicate, outlier, sai kieu du lieu va gia tri null.
