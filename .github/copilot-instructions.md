# Copilot Instructions for AI Agents

## Visión general del proyecto
Este repositorio implementa una simulación de la máquina Enigma, estructurada en módulos bajo el paquete `homework`. El flujo principal involucra la inicialización de la máquina, la configuración de rotores, reflectores y plugboard, y la codificación/decodificación de letras.

## Estructura y componentes clave
- `homework/`: Contiene los módulos principales (por ejemplo, `rotor`, `reflector`, `plugboard`, `enigma_machine`, `constants`). Cada módulo implementa una parte funcional de la máquina Enigma.
- `tests/`: Pruebas unitarias con `pytest` que validan el comportamiento de cada componente y el flujo completo de la máquina.
- `setup.sh` y `setup.py`: Scripts para instalar dependencias y preparar el entorno.
- `requirements.txt`: Lista de dependencias (incluye `pytest`, `black`, `isort`).

## Flujos de trabajo críticos
- **Instalación y entorno**:
  - En MacOS/Linux: `python3 -m venv .venv && source .venv/bin/activate && source setup.sh`
  - En Windows: `python3 -m venv .venv && .venv\Scripts\activate && setup`
- **Ejecución de pruebas**: `pytest`
- **Formateo y orden de imports**: Usar `black` y `isort` según lo definido en `requirements.txt`.
- **Autograding**: El workflow `.github/workflows/classroom.yml` ejecuta `setup.sh` y luego `pytest` en cada push.

## Convenciones y patrones específicos
- Los módulos de `homework` usan funciones puras y estructuras de datos tipo diccionario para representar el estado de la máquina.
- Las pruebas en `tests/test_homework.py` cubren plugboard, reflectores, rotores, rotación y el flujo completo de la máquina. Ejemplo:
  ```python
  machine = make_enigma_machine(...)
  machine = initialize_enigma_machine(machine, offsets=["A", "A", "A"])
  letter = apply_enigma_machine("A", machine)
  assert letter == "P"
  ```
- Los scripts de setup instalan el paquete en modo editable (`pip3 install -e .`).
- No hay clases; todo se maneja con funciones y diccionarios.
- Los tests usan seeds fijos para plugboard y offsets para reproducibilidad.

## Integraciones y dependencias
- No hay dependencias externas más allá de las listadas en `requirements.txt`.
- El workflow de GitHub Actions (`classroom.yml`) está orientado a autograding para educación.

## Ejemplo de flujo de desarrollo
1. Modifica o agrega funciones en `homework/`.
2. Ejecuta `source setup.sh` para instalar dependencias.
3. Corre `pytest` para validar cambios.
4. Usa `black` e `isort` para mantener el formato.

## Archivos clave para referencia
- `homework/` (módulos funcionales)
- `tests/test_homework.py` (pruebas y ejemplos de uso)
- `setup.sh`, `setup.py`, `requirements.txt` (instalación y dependencias)
- `.github/workflows/classroom.yml` (autograding)

---
¿Hay algún aspecto del flujo, convención o integración que requiera mayor detalle o aclaración? Indica qué se debe mejorar o expandir.