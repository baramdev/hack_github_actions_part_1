# ⚡️Hacks Github Actions parte 1 🚀🤓
**Realizado por :** 
### Jorbi Fernandez (`BaramDev`)

## Hacks table 🤔

| Hacks | Details | Status | Links |
|-------|---------|--------|-------|
| ✨ Hack 1 | Saludo desde terminal | ✅ |[H-1](https://github.com/baramdev/hack_g_a_1 "Hack 1")|
| ✨ Hack 2 | Detectar eventos | ✅ |[H-2](https://github.com/baramdev/hack_g_a_2 "Hack 2")|
| ✨ Hack 3 | Condiciones | ✅ |[H-3](https://github.com/baramdev/hack_g_a_3 "Hack 3")|
| ✨ Hack 4 | Uses| ✅ |[H-4](https://github.com/baramdev/hack_g_a_4 "Hack 4")|
| ✨ Hack 5 | Comandos de linux | ✅ |[H-5](https://github.com/baramdev/hack_g_a_5 "Hack 5")|


## 📂 *Hack 1* Saludo desde terminal 
**[🔎 Hack 1](https://github.com/baramdev/hack_g_a_1 "Hack 1")**
```
📁 hack_gh_1
|-- .github/workflows/flow.yml
```
### Script 1 solution ✨
```yaml
name: Saludo
on: [push]

jobs:
  saludo:
    runs-on: ubuntu-latest
    steps:
      - name: Decir hola
        run: echo "Hola mundo desde GitHub Actions"
```

## 📂 *Hack 2* Detectar eventos
**[🔎 Hack 2](https://github.com/baramdev/hack_g_a_2 "Hack 2")**
```
📁 hack_gh_2
|-- .github/workflows/flow.yml
```
### Script 2 solution ✨
```yaml
name: Eventos
on: [push, pull_request]

jobs:
  detectar-evento:
    runs-on: ubuntu-latest
    steps:
      - name: Mostrar tipo de evento
        run: | 
          echo "El autor es: ${{ github.actor }}"

      - name: Mostrar tipo de evento
        run: | 
          echo "El evento que me activo fue: ${{ github.event_name }}"
```

## 📂 *Hack 3* Condiciones
**[🔎 Hack 3](https://github.com/baramdev/hack_g_a_3 "Hack 3")**
```
📁 hack_gh_3
|-- .github/workflows/flow.yml
```
### Script 3 solution ✨
```yaml
name: condiciones

on: [push, pull_request]

jobs:
  ejemplo:
    runs-on: ubuntu-latest
    steps:
      - name: detectar push con if
        if: github.event_name == 'push'
        run: echo "Ejecutando solo en push"
      
      - name: detectar pull_request con if
        if: github.event_name == 'pull_request'
        run: echo "Ejecutando solo en PR"

      - name: Otra forma
        run: |
          if [ "${{ github.event_name }}" == "push"]; then
            echo "Se detecto un push desde script bash"
          fi
```


## 📂 *Hack 4* Uses
**[🔎 Hack 4](https://github.com/baramdev/hack_g_a_4 "Hack 4")**
```
📁 hack_gh_4
|-- .github/workflows/flow.yml
|-- data.json
|-- server.py
|-- README.md
```
### Script 4 solution ✨
```yaml
name: Descargar repositorio
on: [push]

jobs:
  checkout:
    runs-on: ubuntu-latest
    steps:
      - name: Descargar codigo
        uses: actions/checkout@v4
      - run: ls -la

      - name: Descargar proyecto
        uses: actions/upload-artifact@v4
        with:
          name: mi-proyecto
          path: .
          retention-days: 7
```

## 📂 *Hack 5* Comandos de linux
**[🔎 Hack 5](https://github.com/baramdev/hack_g_a_5 "Hack 5")**
```
📁 hack_gh_5
|-- .github/workflows/flow.yml
```
### Script 5 solution ✨
```yaml
name: Comandos Linux 
on: [push]

jobs:
  comandos:
    runs-on: ubuntu-latest
    steps:
      - name: comando 1
        run: |
          whoami
          pwd
          date
          uname -a
          echo "Varios comandos en un solo step"
          ls -la
```
</br>
</br>

***

*<h3 style="text-align: center; font-size: 2.5rem;">BaramDev</h3>*
