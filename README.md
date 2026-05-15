# 👨‍🏫 Teacher Assignment System

An optimization-based tool that automatically assigns teachers to courses using integer linear programming. Built for university departments to streamline the scheduling process each semester.

**[→ Open the app](https://asignacion-docente-vripsanuenmzn8dpnynqjz.streamlit.app/)**

<img width="842" height="752" alt="image" src="https://github.com/user-attachments/assets/ab6aae41-7aa2-4a79-bce9-3f13108d1704" />


---

## Background

This system was built and used in production at [Universidad Argentina de la Empresa (UADE)](https://www.uade.edu.ar), a large private university in Buenos Aires, Argentina, with over 50,000 enrolled students across multiple campuses. Each semester, department directors are responsible for manually assigning dozens of teachers to hundreds of courses — a complex, time-consuming process that this tool automates and optimizes.

The system was developed as a personal initiative and adopted by department directors to plan their course schedules, significantly reducing the time and effort required for teacher assignment.

## What it does

Given a list of courses and a list of teachers with their preferences and availability, the system finds the optimal assignment that maximizes a composite score based on:

- Subject match (preferred vs. alternative)
- Campus preference (preferred vs. alternative)
- Schedule availability (preferred vs. alternative)

All while respecting hard constraints such as maximum course load per teacher, no schedule overlaps, modality preferences, and campus restrictions.

## Features

- **Web interface** built with Streamlit — no coding required to use it
- **Automatic deduplication** of form responses by email and timestamp
- **All-online mode** — automatically detected when campus/in-person columns are absent
- **Manual priority tuning** — administrators can edit the input file before uploading to influence results
- **Unassigned course suggestions** — proposes alternative days for courses that couldn't be assigned
- **Full documentation** embedded in the app

## Tech stack

- Python
- [PuLP](https://coin-or.github.io/pulp/) — linear programming solver
- [Streamlit](https://streamlit.io) — web interface
- pandas — data processing

## Files

| File | Description |
|---|---|
| `app.py` | Streamlit web app — interface + full optimization logic |
| `asignacion_docente.py` | Original Google Colab version of the algorithm |
| `requirements.txt` | Python dependencies |

## Run locally

```bash
pip install -r requirements.txt
streamlit run app.py
```

## Author

Federico La Rocca
