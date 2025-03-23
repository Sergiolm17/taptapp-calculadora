# TapTapp Calculadora de Costos de Impresión

Esta aplicación web permite calcular los costos de impresión basados en el consumo real de tóner, considerando la cobertura de color CMYK y el tamaño de las páginas.

## Características Principales

- Cálculo preciso basado en datos reales de rendimiento: 450g de tóner rinde 60,000 páginas A4 al 5% de cobertura
- Precio actual del tóner: S/130 por 400g
- Soporte para múltiples tamaños de página
- Análisis detallado de cobertura CMYK

## Páginas de la Aplicación

### 1. Calculadora de Costos (/)

- Página principal para cálculos generales
- Accesible desde la ruta raíz "/"

### 2. Calculadora de Impresión de Imágenes (/imagen)

- Permite subir imágenes individuales en formato JPEG
- Analiza la cobertura de color CMYK de la imagen
- Muestra porcentajes detallados de cada color
- Calcula el costo de impresión basado en el consumo de tóner

### 3. Calculadora PDF (/pdf)

- Permite subir y analizar documentos PDF
- Analiza cada página individualmente
- Muestra:
  - Dimensiones de cada página
  - Porcentaje de cobertura CMYK por página
  - Costo individual por página
  - Costo total del documento
- Ajusta automáticamente los costos según el tamaño de cada página
  - Por ejemplo: una página A3 con 5% de cobertura consumirá el doble de tóner que una A4

### 4. Historial de Análisis (/historial)

- Muestra todos los análisis realizados previamente (documentos e imágenes)
- Almacena los datos en el almacenamiento local del navegador
- Características:
  - Sistema de paginación para navegar entre múltiples registros
  - Toggle para expandir/colapsar detalles de cada análisis
  - Filtrado por tipo de documento (PDF/Imagen)
  - Posibilidad de reanalizar documentos anteriores
  - Vista previa en miniatura de imágenes analizadas
  - Datos detallados de cobertura y costos para cada registro
- Permite borrar entradas individuales o todo el historial

### 5. Panel de Control Administrativo (/admin)

- Permite personalizar todos los parámetros utilizados en los cálculos:
  - Precio del tóner
  - Peso del tóner (gramos)
  - Rendimiento del tóner (páginas)
  - Porcentaje de cobertura base
  - Peso del tóner para el rendimiento especificado
- Muestra valores calculados en tiempo real:
  - Costo por gramo
  - Gramos por página al 5% de cobertura
  - Gramos por página al 20% de cobertura
- Guarda la configuración en el almacenamiento local del navegador
- La configuración guardada se aplica automáticamente a todas las calculadoras

### 6. Comparador de Documentos (/comparador)

- Permite subir y analizar dos versiones de un documento PDF
- Muestra los documentos lado a lado para facilitar la comparación visual
- Proporciona navegación independiente por las páginas de cada documento
- Calcula y compara:
  - Número total de páginas
  - Costo total de impresión para cada documento
  - Distribución de costos por color (Cian, Magenta, Amarillo, Negro)
- Ofrece un análisis comparativo con:
  - Diferencia absoluta de costo
  - Porcentaje de ahorro entre versiones
  - Recomendación clara sobre qué versión es más económica de imprimir

## Cálculos y Fórmulas

### Costos Base

- Costo por gramo de tóner: S/130 ÷ 400g = S/0.325 por gramo
- Consumo base (A4): 0.0075g por página al 5% de cobertura
- Consumo normalizado al 20%: 0.03g por página A4

### Ajustes por Tamaño

- Los costos se ajustan proporcionalmente al área de la página
- Referencia: A4 = 210 × 297 mm = 62,370 mm²
- Ejemplo:
  - A3 (297 × 420 mm = 124,740 mm²) costará aproximadamente el doble que un A4
  - A5 (148 × 210 mm = 31,080 mm²) costará aproximadamente la mitad que un A4

## Tecnologías Utilizadas

- Astro
- TailwindCSS
- PDF.js para el procesamiento de PDFs
- Canvas API para el análisis de imágenes

## Uso

1. Selecciona la calculadora apropiada según el tipo de archivo (imagen o PDF)
2. Sube tu archivo
3. Revisa el análisis detallado de cobertura y costos
4. Para PDFs, puedes navegar entre las páginas para ver detalles específicos

## Futuras Mejoras

### Páginas Adicionales Propuestas

1. **Calculadora de Trabajos por Lote**

   - Permitiría subir múltiples archivos (PDFs e imágenes)
   - Calcularía el costo total del conjunto de documentos
   - Generaría un informe detallado exportable

2. **Calculadora de Mantenimiento**

   - Estimaría la vida útil restante de consumibles basado en el historial de impresiones
   - Calcularía cuándo reemplazar componentes como tambores y fusor
   - Proyección de costos de mantenimiento a largo plazo

3. **Optimizador de Impresión**

   - Analizaría documentos y sugeriría cambios para reducir el consumo de tóner
   - Recomendaría configuraciones de impresión más eficientes
   - Opción para reformatear automáticamente documentos para menor consumo

4. **Calculadora de Impacto Ambiental**

   - Estimaría la huella de carbono de las impresiones
   - Mostraría el ahorro en recursos al optimizar documentos
   - Recomendaciones para impresión más sostenible

5. **Analizador de Historial de Impresión**

   - Importación de registros de impresión desde impresoras
   - Análisis de tendencias de consumo de tóner por período
   - Visualización gráfica del uso de diferentes colores a lo largo del tiempo

6. **Simulador de Cobertura y Costos**

   - Herramienta educativa para visualizar cómo diferentes porcentajes de cobertura afectan los costos
   - Permitiría ajustar la cobertura de cada color y ver resultados en tiempo real
   - Galería de ejemplos prácticos con diferentes tipos de documentos

7. **Presupuestador de Proyectos de Impresión**

   - Estimación de costos para proyectos grandes (libros, revistas, folletos)
   - Cálculo de variantes (diferentes papeles, acabados, encuadernaciones)
   - Comparativa de costos entre impresión interna vs servicios externos

8. **Gestor de Perfiles de Impresoras**

   - Administración de múltiples modelos de impresoras con diferentes rendimientos
   - Configuración de perfiles por departamento o uso
   - Comparativa de eficiencia entre diferentes equipos

9. **Integración con API de Sistemas ERP**

   - Conexión con sistemas de gestión empresarial
   - Sincronización de precios de insumos en tiempo real
   - Integración con módulos de contabilidad para facturación precisa

10. **Aplicación Móvil Complementaria**
    - Versión adaptada para dispositivos móviles
    - Escaneo de documentos con la cámara para análisis rápido
    - Notificaciones sobre cambios en precios de insumos

### Mejoras Técnicas Propuestas

1. **Exportación de Resultados**

   - Permitir exportar análisis en formato PDF, CSV y XLSX
   - Generación de reportes personalizables

2. **Sistema de Cuentas de Usuario**

   - Perfiles con historial de documentos analizados
   - Configuraciones guardadas en la nube
   - Roles y permisos para empresas (administrador, operador, etc.)

3. **Panel de Estadísticas Avanzadas**
   - Dashboard con métricas clave de uso
   - Análisis de tendencias y comportamientos
   - Recomendaciones inteligentes basadas en el uso
