# Brand Connect — Navegabilidad (Laboratorio)

Aplicación Android (Java) para Brand Connect, plataforma que conecta negocios locales de Bogotá con microinfluencers. Implementa la jerarquía de actividades vista en clase.

## Estructura de navegación

```
TopLevelActivity (ListView: Campañas | Microinfluencers | Negocios Locales)
├── CampaignCategoryActivity     → CampaignDetailActivity
├── InfluencerCategoryActivity   → InfluencerDetailActivity
└── BusinessCategoryActivity     → BusinessDetailActivity
```

| Capa | Clase Java | Layout |
|------|-----------|--------|
| Nivel superior | `TopLevelActivity` | `activity_top_level.xml` |
| Categoría | `CampaignCategoryActivity`, `InfluencerCategoryActivity`, `BusinessCategoryActivity` | `activity_*_category.xml` |
| Detalle | `CampaignDetailActivity`, `InfluencerDetailActivity`, `BusinessDetailActivity` | `activity_*_detail.xml` |

## Cómo funciona

- `TopLevelActivity` usa un `OnItemClickListener` y lanza la categoría según la posición del ítem.
- Cada actividad de categoría enlaza un arreglo de datos con su `ListView` mediante un `ArrayAdapter`, y envía el `id` (posición) del ítem seleccionado en un `Intent`.
- Cada actividad de detalle recupera el id con `getIntent().getIntExtra(...)` y actualiza `ImageView` y `TextView`.
- En `AndroidManifest.xml`, `android:parentActivityName` habilita el botón «Arriba» en cada nivel.
- Los datos viven en las clases `Campaign`, `Influencer` y `Business` como arreglos estáticos de ejemplo.

## Ejecución

Abrir la carpeta en Android Studio (Hedgehog o superior), sincronizar Gradle y ejecutar en un emulador con API 24+.

## Entrega

Subir la URL de este repositorio de GitHub a Moodle.
