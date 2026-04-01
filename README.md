# DEKU ASSASSIN PROTOCOL — ACTUALIZACIÓN

## ✅ Cambios realizados

### 1. **Intro simplificado** (intro.html)
- ✓ **Eliminé los selectores de fecha** (las ruedas)
- ✓ **Solo pide tu nombre** 
- ✓ El nombre se guarda automáticamente en el sistema
- ✓ La fecha de inicio se establece como "hoy" automáticamente

### 2. **Preload de datos** (preload.html)
- Pre-rellena el progreso con lunes y martes completados
- Suma automática de XP: **126 puntos** (79 lunes + 47 martes)
- Racha de **2 días**
- **12 ejercicios completados**

---

## 🚀 Cómo usar

### **Opción 1: Primera vez (Instalación limpia)**
1. Abre `preload.html` en tu navegador
2. Se cargará automáticamente el progreso con los 2 días completados
3. Redirigirá a `index.html` con todo listo

### **Opción 2: Ya tienes datos guardados**
Si ya completaste el onboarding en `intro.html`:
1. Abre la consola del navegador (F12 → Consola)
2. Ejecuta este código:

```javascript
const SKEY='deku_v3'; const OKEY='deku_onboarded'; const state=JSON.parse(localStorage.getItem(SKEY)||'{}'); state.xp=(state.xp||0)+126; state.streak=2; state.totalExercises=(state.totalExercises||0)+12; state.lastCompleted='2026-04-28'; state.history=[{date:'28 abr 2026',rawDate:'2026-04-28T12:00:00.000Z',dayId:'martes',dayLabel:'MARTES',type:'HIIT',icon:'🔥',xp:47,exercises:4},...(state.history||[])]; localStorage.setItem(SKEY,JSON.stringify(state)); location.reload();
```

---

## 📱 Features actualizado

✅ **Solo pide nombre** — nada de selectors de fecha complicados  
✅ **Progreso guardado** — todo se sincroniza en localStorage  
✅ **XP automático** — lunes: 79 XP, martes: 47 XP  
✅ **Racha activa** — 2 días consecutivos  
✅ **PWA compatible** — funciona offline en tu celular  

---

## 🔧 Arquitectura de datos

### LocalStorage (`deku_v3`)
```javascript
{
  xp: 126,              // XP total
  streak: 2,            // Días de racha
  lastCompleted: "2026-04-28",
  totalSessions: 2,
  totalExercises: 12,
  hunterName: "TU_NOMBRE",
  history: [            // Historial de días completados
    { date, dayId, dayLabel, type, icon, xp, exercises }
  ],
  // ... más campos
}
```

---

## ❌ Lo que NO pides más

- ~~Selector de fecha (ruedas)~~
- ~~Confirmación de fechas~~
- Solo **nombre** → listo

---

Si todo está OK, abre `preload.html` para cargar el progreso de lunes y martes. 🎯
