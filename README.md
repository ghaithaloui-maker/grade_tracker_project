# 📊 GradeTracker — Academic Mission Control

> Un projet Django complet pour suivre vos notes académiques, avec une interface moderne et intuitive.

---

## ✨ Fonctionnalités

### ✅ Obligatoires (15 pts)
| Fonctionnalité | Détail |
|---|---|
| **CRUD Matières** | Créer, lire, modifier, supprimer des matières |
| **CRUD Notes** | Créer, lire, modifier, supprimer des notes |
| **SQLite3** | Base de données intégrée |
| **Templates Django** | Interface HTML avec Django Template Language |
| **Architecture MVT** | Modèle – Vue – Template |
| **Environnement virtuel** | Utilisation de `venv` |

### 🎯 Bonus implémentés (+5 pts)
| Option | Points |
|---|---|
| Page d'accueil esthétique (hero animé, cartes flottantes) | +1 |
| Système d'authentification login/logout/register | +2 |
| Bootstrap 5 (+ Font Awesome + Google Fonts) | +1 |
| Recherche dans les matières et les notes | +1 |
| **Total bonus** | **+5** |

---

## 🗄️ Modèles de données

### `Subject` (Matière)
- `user` → ForeignKey(User) — relation avec l'utilisateur
- `name` — Nom de la matière
- `code` — Code (ex: MATH301)
- `coefficient` — Coefficient (0.5 à 10)
- `semester` — Semestre 1 ou 2
- `professor` — Nom du professeur
- `color` — Couleur d'identification

### `Grade` (Note)
- `subject` → ForeignKey(Subject) — **relation entre les deux tables**
- `exam_type` — Type : CC, DS, TP, EXAM, PROJET, ORAL, AUTRE
- `label` — Libellé (ex: DS1 - Chapitre 2)
- `value` — Note sur 20
- `weight` — Pondération
- `date` — Date de l'évaluation
- `notes` — Remarques optionnelles

---

## 🚀 Installation & Lancement

### 1. Cloner le projet
```bash
git clone <votre-lien-github>
cd grade_tracker
```

### 2. Créer l'environnement virtuel
```bash
python -m venv venv
source venv/bin/activate      # Linux / macOS
venv\Scripts\activate         # Windows
```

### 3. Installer les dépendances
```bash
pip install -r requirements.txt
```

### 4. Appliquer les migrations
```bash
python manage.py makemigrations
python manage.py migrate
```

### 5. Créer un superutilisateur (admin)
```bash
python manage.py createsuperuser
```

### 6. Lancer le serveur
```bash
python manage.py runserver
```

### 7. Ouvrir dans le navigateur
- **Application** → http://127.0.0.1:8000/
- **Admin Django** → http://127.0.0.1:8000/admin/

---

## 🗂️ Structure du projet

```
grade_tracker/
├── grade_tracker/           # Configuration Django
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── grades/                  # Application principale
│   ├── models.py            # Subject + Grade
│   ├── views.py             # Toutes les vues CRUD
│   ├── forms.py             # Formulaires
│   ├── urls.py              # Routes
│   ├── admin.py             # Interface admin
│   ├── templates/grades/    # 12 templates HTML
│   └── static/grades/css/   # Style personnalisé
├── manage.py
├── requirements.txt
└── README.md
```

---

## 📐 Architecture MVT

```
Requête HTTP
    ↓
urls.py          → Routage
    ↓
views.py         → Logique métier (Vue)
    ↓
models.py        → Accès base de données (Modèle)
    ↓
templates/*.html → Rendu HTML (Template)
    ↓
Réponse HTTP
```

---

## 🎨 Stack technique

- **Backend** : Django 5.0 + Python 3.x
- **Base de données** : SQLite3
- **Frontend** : Bootstrap 5.3 + Font Awesome 6 + Google Fonts
- **Auth** : django.contrib.auth (login/logout/register)
- **Design** : Dark theme, animations CSS, glassmorphism

---

*Projet réalisé dans le cadre du module Programmation Python Avancée — AU 25-26 Semestre 2*
*Enseignante : Dr. Sghaier Amra — Niveau : 3E Info*
