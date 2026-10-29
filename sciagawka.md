# Ściągawka — Bootstrap na sprawdzian

Siatka ma zawsze **12 kolumn**.

## Ekrany

Klasa bez skrótu działa od 0. Skrót włącza się od podanej szerokości i zostaje na szerszych.

| Skrót | Od     | Przykład                  |
| ----- | ------ | ------------------------- |
| brak  | 0      | `col-12` — cała szerokość |
| `sm`  | 576px  | `col-sm-6`                |
| `md`  | 768px  | `col-md-6` — połowa       |
| `lg`  | 992px  | `col-lg-4` — 4/12         |
| `xl`  | 1200px | `col-xl-3`                |
| `xxl` | 1400px | `col-xxl-2`               |

Jedna kolumna na telefonie, dwie od tabletu, trzy od laptopa:

```html
<div class="col-12 col-md-6 col-lg-4"></div>
```

## Odstępy

`mb-3` = margin na dole, poziom 3 = 1rem (16px). `py-5` = padding góra i dół, poziom 5 = 3rem (48px).

| Litera    | Co                                    |
| --------- | ------------------------------------- |
| `m` / `p` | margin na zewnątrz / padding w środku |
| `t` `b`   | góra / dół                            |
| `s` `e`   | lewo (start) / prawo (end)            |
| `x` `y`   | lewo i prawo / góra i dół             |
| `g`       | odstęp między kolumnami w `row`       |

| Poziom | Wielkość                   |
| ------ | -------------------------- |
| `0`    | 0                          |
| `1`    | 0.25rem                    |
| `2`    | 0.5rem                     |
| `3`    | 1rem                       |
| `4`    | 1.5rem                     |
| `5`    | 3rem                       |
| `auto` | wypycha na bok (`ms-auto`) |

## Kolory i tekst

Do `bg-`, `text-` i `btn-` dopisujesz: `primary`, `secondary`, `success`, `danger`, `warning`, `info`, `light`, `dark`.

- jasne tło: `bg-danger-subtle`
- ciemniejszy tekst na jasnym tle: `text-danger-emphasis`
- na `bg-dark`: `text-white`, przygaszony: `text-white-50`
- obwódka przycisku: `btn-outline-danger` (zawsze razem z `btn`)
- tytuł strony: `display-5`. Wstęp pod nim: `lead`. Pogrubienie: `fw-bold`

Tło na całą szerokość okna dawaj na `section`. W środku wstaw `div.container`, żeby tekst został w węższej kolumnie.

## Karta

```html
<div class="card h-100">
  <img class="card-img-top" src="https://picsum.photos/400/200" alt="Opis" />
  <div class="card-body">
    <h5 class="card-title">Tytuł</h5>
    <p class="card-text">Opis.</p>
    <a class="btn btn-primary" href="#kontakt">Więcej</a>
  </div>
</div>
```

Zdjęcie: `card-img-top`. Kilka kart: `row g-3`, każda w `col-12 col-md-6 col-lg-4`.

## Navbar

```html
<nav class="navbar navbar-expand-lg navbar-dark bg-dark sticky-top">
  <div class="container">
    <a class="navbar-brand" href="#start">Nazwa</a>
    <button
      class="navbar-toggler"
      type="button"
      data-bs-toggle="collapse"
      data-bs-target="#mainNav"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="mainNav">
      <ul class="navbar-nav ms-auto">
        <li class="nav-item"><a class="nav-link" href="#start">Start</a></li>
      </ul>
    </div>
  </div>
</nav>
```

`data-bs-target="#mainNav"` i `id="mainNav"` to ten sam napis. `navbar-expand-lg` — linki w rzędzie od 992px. `sticky-top` — pasek zostaje przy przewijaniu. Bundle JS na dole strony jest potrzebny, żeby hamburger działał.

## Formularz

```html
<form class="needs-validation" novalidate>
  <div class="mb-3">
    <label class="form-label" for="email">E-mail</label>
    <input class="form-control" type="email" id="email" required />
    <div class="invalid-feedback">Podaj e-mail</div>
  </div>
  <button class="btn btn-primary" type="submit">Wyślij</button>
</form>
```

- `for` i `id` są takie same
- lista: `form-select`
- checkbox: `form-check` + `form-check-input` + `form-check-label`
- dwa pola obok siebie od `md`: `row g-3` i w nim `col-12 col-md-6`
- `novalidate` gasi dymki przeglądarki
- skrypt po submit dopisuje `was-validated` — wtedy widać `invalid-feedback`
- przycisk wysyłający ma `type="submit"`

## Switch

```html
<div class="form-check form-switch form-check-inline">
  <input class="form-check-input" type="checkbox" id="d5" checked />
  <label class="form-check-label" for="d5">5 km</label>
</div>
```

`form-switch` robi przełącznik. `form-check-inline` stawia kolejny obok, w tym samym rzędzie. `checked` włącza go na starcie.

## Na egzaminie INF.04

Arkusz podaje gotowy HTML w tabeli. Style podłącza się tak:

```text
import 'bootstrap/dist/css/bootstrap.css';
```

```text
@import "~bootstrap/dist/css/bootstrap.css";
```

Pierwsza linia jest do Reacta. Druga do Angulara, do pliku `styles.css`.
