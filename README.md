# 🥗 INTAKE

## 🚦 Estado del proyecto

**INTAKE v1.0**  
La aplicación ha alcanzado su **primera versión estable**, con todas las funcionalidades base implementadas y operativas en entorno de producción.

Incluye:
- Gestión completa de clientes
- Creación y edición de dietas
- Cálculo automático de macronutrientes
- Generación de PDFs profesionales
- Compartición segura de dietas mediante enlace
- Interfaz responsive y coherente

A partir de esta versión, el desarrollo se centra en **mejoras incrementales y nuevas funcionalidades**.

---

Aplicación web para **gestión nutricional profesional**, orientada a entrenadores y nutricionistas.  
Permite crear clientes, diseñar dietas por comidas, calcular macronutrientes, generar PDFs profesionales y compartir dietas mediante enlaces públicos seguros.

---

## ✨ Características principales

### 👤 Gestión de clientes
- Crear, editar y eliminar clientes
- Información de contacto (email, teléfono)
- Notas personalizadas por cliente
- Historial completo de dietas

### 🍽️ Planificación de dietas
- Creación de dietas por **comidas diarias**
- Selección de alimentos con cantidades en gramos
- Cálculo automático de:
  - Calorías
  - Proteína
  - Carbohidratos
  - Grasas
- Dieta activa + histórico de dietas anteriores

### 💊 Suplementación
- Asignación de suplementos por comida
- Cantidad y unidad configurable (g, mg, cápsulas, etc.)
- Visible en app, PDF y enlace compartido

### 📝 Notas y recomendaciones
- Campo de notas por dieta
- Ideal para:
  - Indicaciones generales
  - Ajustes personalizados
  - Recomendaciones específicas
- Visible en app, PDF y enlace compartido

### 📊 Visualización de macros
- Resumen diario
- Gráficos visuales (donut de macronutrientes)
- Totales por comida y por día

### 📄 Exportación y compartición
- Generación de **PDF profesional**
- Enlaces públicos de dieta (sin login)
- Vista responsive para móvil y desktop

### 🔐 Autenticación
- Login privado con Supabase Auth
- Acceso restringido al panel profesional
- Enlaces compartidos aislados por token

---

## 🖼️ Estilo visual

- Modo oscuro por defecto
- Identidad corporativa:
  - Fondo: `#0B0B0B`
  - Texto: `#FFFFFF`
  - Color acento: `#1E90FF` (azul eléctrico)
- UI consistente basada en cards
- Totalmente responsive

---

## 🧱 Stack tecnológico

### Frontend
- **Next.js 14 (App Router)**
- **React**
- **TypeScript**
- **Tailwind CSS**

### Backend / Base de datos
- **Supabase**
  - PostgreSQL
  - Auth
  - Row Level Security (RLS)

### Generación de PDFs
- `@react-pdf/renderer`

---


## 🗄️ Modelo de datos (resumen)

### clients
- id (uuid)
- name
- email
- phone
- notes
- created_at

### diets
- id
- client_id
- name
- notes
- created_at
- is_active

### diet_meals
- id
- diet_id
- meal_index

### diet_items
- id
- meal_id
- food_id
- grams
- role
- parent_item_id

### diet_supplements
- id
- meal_id
- name
- amount
- unit
- timing
- notes

### foods
- id
- name
- kcal_100
- protein_100
- carbs_100
- fat_100

### diet_shares
- id
- diet_id
- token
- is_active
- expires_at
- created_at

