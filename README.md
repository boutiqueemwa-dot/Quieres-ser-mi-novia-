<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Para Io Inti 🌹</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300;1,400&family=Great+Vibes&family=Playfair+Display:ital@1&display=swap" rel="stylesheet">
<style>
  :root {
    --rose: #c8536a;
    --deep-rose: #8b2040;
    --gold: #d4a853;
    --cream: #fdf6ee;
    --dark: #1a0a10;
    --blush: #f5dce2;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--dark);
    color: var(--cream);
    font-family: 'Cormorant Garamond', serif;
    overflow-x: hidden;
  }

  /* ── Partículas de pétalos ── */
  .petals {
    position: fixed;
    top: 0; left: 0;
    width: 100%; height: 100%;
    pointer-events: none;
    z-index: 0;
    overflow: hidden;
  }
  .petal {
    position: absolute;
    top: -30px;
    font-size: 1.2rem;
    opacity: 0;
    animation: fall linear infinite;
  }
  @keyframes fall {
    0%   { opacity: 0; transform: translateY(0) rotate(0deg); }
    10%  { opacity: 0.7; }
    90%  { opacity: 0.4; }
    100% { opacity: 0; transform: translateY(110vh) rotate(360deg); }
  }

  /* ── Hero ── */
  .hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 3rem 1.5rem;
    background:
      radial-gradient(ellipse at 50% 0%, rgba(200,83,106,0.25) 0%, transparent 70%),
      radial-gradient(ellipse at 20% 80%, rgba(139,32,64,0.2) 0%, transparent 60%),
      var(--dark);
    z-index: 1;
  }
  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M30 10 C30 10 20 22 20 28 C20 34 24.5 38 30 38 C35.5 38 40 34 40 28 C40 22 30 10 30 10Z' fill='rgba(200,83,106,0.04)'/%3E%3C/svg%3E") repeat;
    z-index: -1;
  }

  .crown {
    font-size: 3.5rem;
    animation: float 3s ease-in-out infinite;
    filter: drop-shadow(0 0 20px rgba(212,168,83,0.8));
  }
  @keyframes float {
    0%,100% { transform: translateY(0); }
    50%      { transform: translateY(-12px); }
  }

  .hero-title {
    font-family: 'Great Vibes', cursive;
    font-size: clamp(3.5rem, 10vw, 7rem);
    color: var(--gold);
    text-shadow: 0 0 40px rgba(212,168,83,0.4);
    line-height: 1.1;
    margin: 1rem 0 0.5rem;
    animation: fadeIn 2s ease forwards;
    opacity: 0;
    animation-delay: 0.3s;
  }
  .hero-sub {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(1rem, 3vw, 1.4rem);
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: rgba(253,246,238,0.55);
    animation: fadeIn 2s ease forwards;
    opacity: 0;
    animation-delay: 0.8s;
  }
  @keyframes fadeIn {
    to { opacity: 1; }
  }

  .scroll-hint {
    position: absolute;
    bottom: 2rem;
    font-size: 0.8rem;
    letter-spacing: 0.2em;
    color: rgba(253,246,238,0.3);
    text-transform: uppercase;
    animation: bounce 2s infinite;
  }
  @keyframes bounce {
    0%,100% { transform: translateY(0); }
    50%      { transform: translateY(6px); }
  }

  /* ── Divisores ornamentales ── */
  .ornament {
    text-align: center;
    font-size: 1.6rem;
    color: var(--gold);
    opacity: 0.5;
    margin: 0.5rem 0;
    letter-spacing: 0.5em;
  }

  /* ── Secciones de texto ── */
  .section {
    position: relative;
    z-index: 1;
    max-width: 780px;
    margin: 0 auto;
    padding: 4rem 2rem;
    text-align: center;
    animation: slideUp 0.8s ease both;
  }
  @keyframes slideUp {
    from { opacity: 0; transform: translateY(40px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .quote {
    font-size: clamp(1.5rem, 4vw, 2.4rem);
    font-style: italic;
    font-weight: 300;
    line-height: 1.6;
    color: var(--cream);
    position: relative;
    padding: 0 1rem;
  }
  .quote::before, .quote::after {
    content: '"';
    font-family: 'Great Vibes', cursive;
    font-size: 5rem;
    color: var(--rose);
    opacity: 0.3;
    position: absolute;
    line-height: 0.5;
  }
  .quote::before { top: 1.2rem; left: -0.5rem; }
  .quote::after  { content: '"'; bottom: -1rem; right: -0.5rem; }

  .highlight {
    font-family: 'Great Vibes', cursive;
    font-size: clamp(2rem, 6vw, 3.5rem);
    color: var(--gold);
    display: block;
    margin: 1.5rem 0;
    text-shadow: 0 0 30px rgba(212,168,83,0.3);
  }

  .body-text {
    font-size: clamp(1.1rem, 2.5vw, 1.45rem);
    line-height: 1.9;
    color: rgba(253,246,238,0.8);
    font-weight: 300;
  }

  /* ── Foto individual ── */
  .photo-frame {
    position: relative;
    z-index: 1;
    max-width: 420px;
    margin: 2rem auto;
    padding: 1rem;
  }
  .photo-frame img {
    width: 100%;
    border-radius: 4px;
    display: block;
    filter: sepia(15%) contrast(1.05);
    transition: transform 0.6s ease, filter 0.6s ease;
  }
  .photo-frame:hover img {
    transform: scale(1.03);
    filter: sepia(0%) contrast(1.1);
  }
  .photo-frame::before {
    content: '';
    position: absolute;
    inset: 0;
    border: 1px solid rgba(212,168,83,0.3);
    border-radius: 6px;
    pointer-events: none;
    transition: border-color 0.4s;
  }
  .photo-frame:hover::before { border-color: rgba(212,168,83,0.7); }
  .photo-caption {
    text-align: center;
    font-style: italic;
    font-size: 0.95rem;
    color: rgba(212,168,83,0.6);
    margin-top: 0.75rem;
    letter-spacing: 0.1em;
  }

  /* ── Galería en fila ── */
  .gallery-row {
    position: relative;
    z-index: 1;
    display: flex;
    gap: 1rem;
    max-width: 900px;
    margin: 2rem auto;
    padding: 0 1.5rem;
    flex-wrap: wrap;
    justify-content: center;
  }
  .gallery-row .photo-frame {
    flex: 1 1 260px;
    margin: 0;
  }

  /* ── Separadores de fondo ── */
  .bg-band {
    position: relative;
    background: linear-gradient(135deg, rgba(200,83,106,0.07) 0%, rgba(139,32,64,0.12) 100%);
    border-top: 1px solid rgba(212,168,83,0.08);
    border-bottom: 1px solid rgba(212,168,83,0.08);
  }

  /* ── Pregunta final ── */
  .final-section {
    position: relative;
    z-index: 1;
    min-height: 80vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 4rem 2rem 6rem;
    background:
      radial-gradient(ellipse at 50% 50%, rgba(200,83,106,0.18) 0%, transparent 70%),
      var(--dark);
  }
  .final-question {
    font-family: 'Great Vibes', cursive;
    font-size: clamp(2.2rem, 7vw, 4.5rem);
    color: var(--gold);
    line-height: 1.4;
    text-shadow: 0 0 50px rgba(212,168,83,0.5);
    max-width: 800px;
    animation: pulse 3s ease-in-out infinite;
  }
  @keyframes pulse {
    0%,100% { text-shadow: 0 0 30px rgba(212,168,83,0.4); }
    50%      { text-shadow: 0 0 70px rgba(212,168,83,0.8), 0 0 120px rgba(200,83,106,0.3); }
  }

  .hearts-footer {
    margin-top: 3rem;
    font-size: 2rem;
    letter-spacing: 0.5em;
    animation: heartbeat 1.2s ease-in-out infinite;
    color: var(--rose);
  }
  @keyframes heartbeat {
    0%,100% { transform: scale(1); }
    50%      { transform: scale(1.18); }
  }

  /* ── Línea decorativa ── */
  .divider {
    display: flex;
    align-items: center;
    gap: 1rem;
    max-width: 400px;
    margin: 1.5rem auto;
    opacity: 0.35;
  }
  .divider::before, .divider::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--gold));
  }
  .divider::after { background: linear-gradient(90deg, var(--gold), transparent); }
  .divider span { color: var(--gold); font-size: 1rem; }

  /* ── Responsive ── */
  @media (max-width: 600px) {
    .gallery-row { flex-direction: column; }
    .gallery-row .photo-frame { flex: unset; width: 90%; }
  }
</style>
</head>
<body>

<!-- Pétalos flotantes -->
<div class="petals" id="petals"></div>

<!-- ══ HERO ══════════════════════════════════════ -->
<section class="hero">
  <div class="crown">👑</div>
  <h1 class="hero-title">Para Io Inti</h1>
  <p class="hero-sub">con todo mi corazón</p>
  <span class="scroll-hint">↓ sigue leyendo ↓</span>
</section>

<!-- ══ FOTO 1 + APERTURA ══════════════════════════ -->
<div class="bg-band">
  <div class="section">
    <p class="body-text">
      Io Inti… desde que te conocí,<br>
      supe que había algo distinto en ti.<br><br>
      Eres tan brillante como las estrellas,<br>
      de esas que iluminan incluso la noche más oscura.<br>
      Y desde el primer momento… <em>no he podido dejar de pensar en ti.</em>
    </p>
    <div class="ornament">❧ ✦ ❧</div>
  </div>
</div>

<div class="photo-frame" style="max-width:380px;">
  <img src="data:image/jpeg;base64,/9j/4QBYRXhpZgAATU0AKgAAAAgABAEAAAQAAAABAAAEOAEBAAQAAAABAAAEOIdpAAQAAAABAAAAPgESAAQAAAABAAAAAAAAAAAAAZIIAAQAAAABAAAAAAAAAAD/4AAQSkZJRgABAQAAAQABAAD/4gHYSUNDX1BST0ZJTEUAAQEAAAHIAAAAAAQwAABtbnRyUkdCIFhZWiAH4AABAAEAAAAAAABhY3NwAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQAA9tYAAQAAAADTLQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAlkZXNjAAAA8AAAACRyWFlaAAABFAAAABRnWFlaAAABKAAAABRiWFlaAAABPAAAABR3dHB0AAABUAAAABRyVFJDAAABZAAAAChnVFJDAAABZAAAAChiVFJDAAABZAAAAChjcHJ0AAABjAAAADxtbHVjAAAAAAAAAAEAAAAMZW5VUwAAAAgAAAAcAHMAUgBHAEJYWVogAAAAAAAAb6IAADj1AAADkFhZWiAAAAAAAABimQAAt4UAABjaWFlaIAAAAAAAACSgAAAPhAAAts9YWVogAAAAAAAA9tYAAQAAAADTLXBhcmEAAAAAAAQAAAACZmYAAPKnAAANWQAAE9AAAApbAAAAAAAAAABtbHVjAAAAAAAAAAEAAAAMZW5VUwAAACAAAAAcAEcAbwBvAGcAbABlACAASQBuAGMALgAgADIAMAAxADb/2wBDAAMCAgMCAgMDAwMEAwMEBQgFBQQEBQoHBwYIDAoMDAsKCwsNDhIQDQ4RDgsLEBYQERMUFRUVDA8XGBYUGBIUFRT/2wBDAQMEBAUEBQkFBQkUDQsNFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBT/wAARCAQ4BDgDASIAAhEBAxEB/8QAHQAAAQUBAQEBAAAAAAAAAAAABAIDBQYHAAgJAf/EAEsQAAEDAwMDAgQDBQUHAgUBCQIAAwQFBhITIjIHFEIjUhUzYnIIJIIWNENTkgElQaKyERdEYWPC0lTiJjVz8PIYMVGDJwkZIVWj/8QAHAEAAwEBAQEBAQAAAAAAAAAAAAIDBAUGAQcI/8QAMREBAQACAgIBAwQCAQMDBQAAAAIDEgQiEzIFARRCBhEjMzFSFSEkQQcWYiVDUVNy/9oADAMBAAIRAxEAPwD03Mppe5AhGwJWuZDIOSr88MC2rzdU6WpozwFQNePMFLPSRBpVmsTxMcMlGa3JSuvHmSQB4pHuSfNbJZU1SnvzTX3L0RYYD2rW4V5lZMgICHwWx2NdohHAck+z69GU14QY5Jiq1IQaVMpt2tPMck1PresG0lbzrapI6xv2os6l6SqUbeeSNeewFGx/GNmTBPaoKTjiaX3m/mhJjw4HuSVS0yr8xnmqfckMgA3Vc5MkTVRvOe0zD5b0iNKaDyIgT+2lAShwk7k6D29SY2q0q4Q7cNynqVUu8fDdsWY0T8yAAK0iiQxgYKuI+rVreeHYrlGMcFltEqWiavFKqWeHsXSx0SpWJck6w4IR6ZgRblo2+hNS5L3NVmqnmBpcytiDpjkKjJk8Xh2kuXlz9jzKpVvIHTJVd6SRmrhWP8FVHmR1VyqpbV+xo2aRPgFpbRU1AZFFzGR7dJqfXqzeZkzmo/vMFO15kQzIVRZkn80Y5I1RpO98KLjTFWWXlJxjWapIuFKniBgrnAnjjksvjPKwU2pEG1RhaWkRpgmjWXlV6bMwDd5KYZmCt8tSwMvIgzUJGmexF94RrTL5qINIe4JOsuMxwT7PoQzSANc9wQ7J719AjPepCAe9Csxs1JRo2CrJBwbxQk+NmKNBJk/KNWT2ZZdrOAGs6N7Alot/vCyw6SyfudY0I1STzXAaB1/qXd1/yTETDLy1OxpIhH5LFwkq22rcPZugJEqbaB6LgPCYI0FRaDcOthgSuUZ4TWzHW5NRa5cuViOXLlyA5cuXIDly5cgOP+z/AGJozSj4IKS9gKnVarTJEySINHuWVX5Uh0DFXCvVXRaMsli921snnTHJc7JkbJlUp+93NNBwSnnkPrLMoLAM+KstHpuDW4d6jKDDF48iV2psNFGSVHDAFNgo+GyIKTAFGjmT2KPnvbTUhM2Aaq8+ZgRilBJvZrgZTMb+3MlJgAqREecPM+KEepv+0+KsGIpOQr7NFR8CjiakDog4ohk8DyyREmS1pclaaCiXJRAAMlnlYPRPatRuepMAwayGsTNZ3bwVppip0CZhIyJWuBWGjAFn+e9SUAywWbPhmyL2c8TBCHMUUy8l+a5Wi0pUJOakIxqEi/4qQA19WlMAaaeNBdzglZ5+SaZULz3p3WwQpnihze+pW1CQOSka29RRyfqXMyd/JHiCYA1zx7EOyaUZ7DWb8gTrYEpiBW8GsclAvKPeewPktkUFmqVVF5rkqfJezdMkh6Z9SH1t61BJw95Gp2BsDJV+mnvVgAxBZwmwmDgkPSRUOb2Bcl2snfNkhnmlggQeRbJpdSiw4J0JIgmgUfPPBASD1SHE1HhJ3ZIHPNcBq51jhzBw4os5448VXAk4eSd7kj8k2oESXtYjUeaLzQ72wUShQfucCXdzmgnj3rgNPTMIToHihM0vNZqWlIA9vUhDk4AoLWRUZ5RaZTxzMBUeb3NIzzSE8n2LA96NZNR4Itk0xRYPLp8kQimh81H1uYLLGCaPciuVV4TIyVfkmi58lQj0ldqJQo6ZpozQ5yUjWWlEQbyFM1xvIQ5KcCANchAeXID0XVQwVSqR4K4Vg8zxVUnwyeXmK7ulSuTz2Kn1V7erdW2SjDuVJqpqOOezNQI3kjPehzNLA1s2JqNA1LU2pFDUCBogHkp9WwWrW+5Y5K0RpmZ7iWP0GsdtHxyVgjXIYHlkqytLWI0nYh6xWGozW0lTY1yNHHy1VA3Dc+ttEv1qx9l4ZrAvbslG1usYCeJKnw6kWl81M1Kq5tFkSkNjT12kBHsVXrFedqruJcE1MeUYZ70M1DWT4ogHkEyaIzUKJK4WZJEJQZEtThvCfksHhzyhu5CSsEC9nYx7i2J5pRuEOTm6OKutNmaOCxS3rwaPk7vWgU2vCbQGJZo8+gaN8YIBVZuG4e2aPcgjuETHkqPcleHeOXJJkz9U9Q8++c5RrgvwVm9Sk/mjxJBHJdPyXN3Js0qZeYPGhTrwve1URl4vciDkkHkjYbNIgV4QayyUg9Xh0OQrJArDrO0SR0atke3JW2Wmlir1SF5o8VnUx7OQZKyyZOYKtTGd+S0zRKERj3qdhhsVdgBm6Aq1Q2dgLHnrsiOjAp2mw9qio39mBKxQD2gozUtMpCMZAKJ78gQ23FNHsJbJaU7GmEpAJOHkq0zPEE69W9iKrQLH3yX8SVROq5gkhVfqSecq4HJzTsYN6q8afn5KbgTPea0zQWhkBBFA80Hkq/3/ALTSwkktk0nqsQPCaTMP0jUezJJdMknpGn2GrN+pAZxzxWSBsJa3ex6zBrJDP1TRsjUiM01muBciaTLA1IRj3qMDYi2TRT7q02xp7uYZGtlo8kXmgXn21akMYg3LYrbqom0G7ercahUrwCWhI0wTBLN4V0tkdRC5Cdz7VwSV82Gotch9ZL1s041OrkhcZ7F8/YGnntqhKlMwaNSEl7YaplwzyADWLPTTjlWrqqog0ayWe93MoyUxeFbI5BiJKr9zmsDZLpOxAme9PSXgxUfrIJS4USTgCvUCYACG5ZFAmEBclc6PUswxIkmx5aFGkipCNJFUL4kQI2BcOjtIkp1rnvbTVEqskQf5KWk1vWDlsVMrE/uZpigLBAnjgje/2KCpTJY7lIPBgKhRDoVXfuJLOqjiq+89gaEen7Vj2omyeOvbtpIGZcJe5V85Je5CyZnpLTFI1QS4a27JDHJVp57ciqk9moV55b5ZqoUBiZqVgcFXQewNStNmZliky+olaGeCeQMaSJjyRDzwh5LkNMiweEEvvx8SUC9M5bl0Z7NNq+rAEnMkcyagWXlJsvcFGqWGmhXgRQHkuMEnlCNMFzIIgwSMFpnLsQWyeCdzQQcE7nsUaO541FTDUg8exRUjmjHXYATNdnvSD5rluA6A96qnQeVfh7DUqBoML1kQBqMzS+6/5Kko0lQNfoSSBRwSUl54sFbV9ToVUcUPJklJPEVFQ8nncVcqJRBMdV1GppQQQyDcSQ9sJXCTTRw4qpVsxZdxRL6H1kQyajweRDJqz5skwNCST2GlgaZePMUopGvGuAyXSOaRmoUxHQNPAaEBdmsy8yLzTrLyEA08BqK6VB5OqPZNFgatNAQAJ0FwGv0+C1B+G8q/XpOYGpt75RqqVJ7MjyVcE9k6Vqe8od55SdSPeq/Je3rsSzUIA12shwPYkGexOiW88hDe3pDz25Cm9vTgaDy5Bay5B3prW7l370QdK2ZKKtt4ZOBZK54CYLzjpMvvCNg0ssquxbHfOIZrGa3JHVWdJD5pYGhNbelg8nA0DT2aEA06Br7sB0aSbJ7SUgzMdMuShg5o5k96JoJsJOA8kiTk9xXMs5otmH5LfIMw4b+CTMjOeSmowYDiSCqpizyT6hT5+WSj896NnvCbqC81GkKEMvIjNBAiAWbY8nQ2Jee9M5rjNJsKSEaY6ye0le6DdTrLQCRLN2XlY6P/AIrNkpFoX7Wu4ciUFUqxrZ5IdnghJmJrNsfZGvPZu5LgNNPc1+MmlZhzJohCAiFPY5BxktkME6CXgn2MWB7EO8GYpWaazzVpp9p0NnCRkrHGMVAsmjgk4LNnrdFOsnvUgzMIMFXGZikGZiwdoWmljCpYAh3qxgoc56j5MxacWemnZNnWEydSVf7xL7nNWrKTZYAqRJ3vlX2ZKLCSKSRsstNmZqYjTyDyVPjTMFJs1Jb5yaHml4gScw3KTZe+pVSBMUn3+3aredZYAmYeSRJn5tHuVcOpYCoeq1t3HFpaZooK86q0DRhks0B7PyR1zzJMx3dwUCCuy0lgeSNZCAaXmvmyYjNEMvKPzToGnUlNxpJBuElfbPucmTASJZky8pOHMJkgMVJ8eiI1eExAsk/8eD3isipV1FpYuki3rq0R5JvPQaqFYE08FSH3LHwvbdyVgh3brNBuT+Wg0X4qOfIUbGqQn5LOgrwmeREpNm4Wg4up55OpdWgBJ28kPJqQh5KmPXUINbnVXJ9+D/NFPXNl91aG9UhVUuTfHNR9KupqY1yTVYqoHHd3eKzeXdZilySfz5qK1kXcjwvVI8VGcErRNFyXtuKHA0gz3prNOVIMnvU1AmaKroGimZOHkovkrn8S9Lkgnphe5QgTPqSDk/UvknTwVJ3DkhDmDq5EoTu/qJJOeralaFTZ4mIFkiJM8dLks6h1h0Ngki/ipH5JKkJqTMzPkhXntqjAkrjkrH4kS3nlHyZPNIkyVFSZO9WmU6ImPKMNLeNNAfitkokZp2MeDuSSYbEgE9BOxpmA8ks6kopk1xmsGphveZkjYzyhQPeimZOCK9X3ZYAk4ImNM38lCMvEaNZXNqVtllhyc/JHG9sVfZewSjkkk1USbz31JrWUP3O5OhJTzISYPfUndZRWsnQkp6OkDNR8r/BcclCSZI+5Rx+wNHzXACHzzJOga3yYWyCLA0CBrtbBMdIayaM0OElLzVJRo6D2C45KEM013X/JWllTFNmCzI3LRaJUmDaAcljncGi4dYfjHtJPS802OfVWmWDLJZ1VZhSZRkhPismTtIknmCjsNtzrLyKB5BBsS81aSpIHkl57ZyQ4GmXj5Jwaee+pcBoQz3p5lZqTkQBpSSCUaxrlgaWB4plLBFAWyaNZPNRjKkGTSScdmlZofNLA962TSex1/wDdzVKqR+qatdSmaMVUGpSd5rZgp9RVSe3KvvH6po2e9vUUZ+qurLLQjPYmjeTJmmjPYrIueeTWaZM0lOBQfcuTQGuUVW8WZVQjAAkrrJuEQaMslitEre0BFWgJj8kMF5jZ0A94VspLpiJLL6q8XcGtSet4j3EO9UK8KP2BmSfUmqqGaSB70g0gF8Kk2TTuajwNEZ8FKqOOA0bDe/MBkooDSu5IDyySTQXuAYmKkPsVCjV53VARLNabbcMpjAuu8yXVxUEe9kAZKpVupO+RLVZlEE457fBZPdsAmZBj4K1PlK6ckjX5rbEOexJA1mplSDJooDUaB8EUBrNVLyLzS80Pmu1lEUKZVggHgq6zJH3KVjTOCzZGVZQmbUl481HsvIjPMeayvuwF4N65kEQYLgBLsieANidDYKHzEEg5P1L4eRwGuN5R/d/UuB5AG6y7mgkoHsFTYDgSs0L3P1JfcAvgHsmjmXtqhweH3Ipl76lnqTDjeQLz3NEc0FJBICNZPA8gc8EsDVgN1jS9YsEhkM09go7BwTCA1JRqkoUwwJcye9bJ7vs0uTNSIA5Keo8kpIclR42Zq228eBgJK0y0zS0BAzBR8+lCHirAyY4qPrEkQDJdWak9M3uSAINGWKomY5K7XhWBCOYiXJUED3p9mahGe9LTSUC+jUQCeBDglAabZQQBokHiBApesvqdJUJhJ0HjPyUUD31Itl5NqidPYSlabVSZ2qHM08y8IGivULR8YJK+PEyq/wBzt5IKTPLiuVVKpOsXI+e3VJQPxJ97kSFkvE8aZ1hBGr7sscO5HYAeSaqV5vvRzaAlXHpOzkgtbPyVpUFdyTx5Ekm8h9bBIN5amhxmkJKUCAIA0vND+C7NZyjQPFJN5D5pBnkqSnTjeJNayUbJJo2SBWmpGwhl5Fg8SjARsben1fRHcGh3pKIMNijXgwSakKeeLBR8k96O5ggZgbEm3ZOgpmuBD570QyrElxpkD3oh4NiFwwJJVH1GgaWhwNKM1JMtLQ+tgSdA8lCn1Jw1MMqEjGpMHtix0ukM0y88he6/5JBvZolIvWzJEAajg5osDSVQEGZAhzmYJMl76lGPPK091Nkh3i7WzUYBl7k8Bq2p5GgadA0KBp0EUtIvW2Ls81wJ3RSbH2NBkikkGUpWmmOqNPIIzRTxoIzzJaZpHYjNLZMjJNGnWUlU+JiMexGgaigk4DyRAScy5JNlJpJrkOD31J1PsfYvWwQkmTzSJL2CinpOZc1QlUI7nci4z2ah+aNgHganU9RKbBckM8EtY1ygS/BI4JYIOWGxEA9gh0yaeQkwkogHlCAeKOZeSZUKoJcMzBrBUefJ5krBcMks1TJknNdLiT1JsCmPe5R+adkmhc125ROmaHM0szQ5mnBBnvSM008a4E4kaC5NAuUdjLLbEzOaH3LWKDG7l0Fh9Nmds+GPuW0dPXimABLysugvwUcXmgVE6l29nAMhFaxDjekq1e2l8NdEseK2aneVHthmPtQ+e9G170alI+9Rue9ZqR1GgaIBCMnmSkOCzUfVwJJglZClshmk2GpdKZzlAS2W1ZghHAVllNZEHQNWiNVSZDlsXVxWfVpEyZ6WALP7tZak5+5d+0hGGOSjZ8/WzzWnbclSok/YeCEDJEVIxOQfsQoGo0xCgRAGhwTwLA0HdZIN5NGaaM0PlHe5LNTtKeI1V9bAlMUqeOaSpZqW5nYiAe3qMCSl6/1LBRElmkmeKHB7byTJyVEHjk7kO89mhzeSgNW2B5nIyUkDKFhqVDgs1UQJhghzRr3BRUl7DcjHW5zxvYJk5ggaj3piHOStmpk2ExSEaSq0zJUrDkpKCysnsSXsUJGk7EszWCih3uaUymjRDKfYDWTRCFB7BK1lnMS8iqPAKe+AiheauFmMgBgWC6nGUlNRrdwaDakyY3YHkrQBjpKs3PMHDEV2skzq0zJIVsgHkoqsV4jaxyUCczfyQ7z2Yclwqz1FikFW5JPO4kowDRdV55IEDXbxVvKQsEtIZ3ojBFUHAaWkYJaTY5WRJJrs1ytNJ0QB4o1l5R/mi2TWyaZqG5rtZDmaHOSo5AOOZtQj0kfcoyZMUac9YNRsmHp+Hmo96pIF57NDnkragWc8ksJOajzAlwGWaeZEpXNLDeh2TzUhGZzNW1aZojRXYKwRqI+8HyiwUlDsx+ZFN1ppw/sFHjPspSXhsV9h9JavMwd0NEPYexWOTbdDtuhmMlpqTN8Q1UeNRjTx4Lo39uZK1BDoc+UbTsZ8Dx4Nb08HTeS81rxhd7fngfMUeKtepEZAh9ztUh8BLDirLR7P+U0ZPsvHxzFW6HYD4Rcn3czH9OS5v22fZ82Y9MoLofKFE0q2JzzoDpc1sp29hHyHtoEcORmWZqvz58mlVQIdMhvz8xzKX4Cu3ixdew2QUbp6Uk8XXx28sFGVWwI0YzF+cTIeOYrUKPbdcN3XaktQ4n27zRrNtsaulJqDk90d5aQrTWJBgsyz5MBrVaLvI/8ANa8FWZ4YZr1tDCmQGtJpoWWvLP8A8FD1i0raqpOsOw4wZDgLzWw8lza43bYPIh80QytIv/ozOtgTmQyGfT/eHNpZoGQJ6KLe4IQ+aeM9iEM96ktQgFxpoD2JGe9IgdwRbIJpnejWQWKqOIZ2Clm9glAGxDzNjRrNNbPuxJzB9yUD2fFQ+t6qLZeVqJslWUXuxQUZ7epIAzFcqsnZ8RskyzQmalZMZQ8n+3Al0sFASHBOoSM8iwPJa2rG4DxRTJoXBEMpaWSDKKzHFBMmuN4lGiUIek4Ifuv+SCekobuDTzLHSRN7NMve5NA9vRHMFoICMySgewXSQQvBIQb3hAkd4We5BayQGS+6hY4ExSfebVV4z2CKOSWCD7HqlP3qMCTmSHmPEZpqM9vWwiwM7xUhDZ3qMhmpiHzWalpGs8E8keC7zUWmTvmlguANi5RULQ5nvTp8EI8nlOqLz3otk9ij07ng1kimalaueTg6qi89mpavTCOUagTNdvjT1fDT29Dp0zQ5mt+xSTNDmaU8aFeNOCDPenWUL5ogE4FMmuXAuUjEsnuBbR0xqTQRwElh7KuVn14obuOS8jjrR0HptmqiDW0lnnUW5BCLjlvUeFzk8AYkqrdurMHPctnk3GzL6xPKTNdJR+tv5J2qgTL5iSj896mVNw5KkO5HDkoGMexFgalSqQB7NFsvKMZRAGo6hOw5ggpAJIvCq0zJUnDNPs045TAM4bkDPMszRYPbE09iYpJztni3lVJgIQDxU3MjbTUOfNafLu5WXBoIA07mhc8E7mhIs0O8nTNCPHyQ+UaM8yRsPNBApiGGeCTJXVjqknGeJSDJoeMyjQjLlVlZiw3rjToBiuMNijscFgnQ2LjTWatsEgy9gpBmYoRk06ElRoJgzzFQtSPDNOnJUZUnuafFJ0brb+SIA9ijM96kI29dGhsdA0XGewND4JYLPSSwQ3vqUkB5iq/GPYpBmTgsFexkhzS88EF3I+5d3I+5KcaDyIA1GBJH3J4JKQJLwUnSqr2Zh7FBA9mnc1XHWlHXU7wIGj3EqvVbhck+ainnvqUe89uW+s+8rbDTmfUnu52qJAyTwGsP5qBKk9tUYEncjZ/BQuZAa9BxqZ1gjSVIAar8M1KsvK1SvKQSTSANLWZ9IXGexcknwVpoBHpO9OsyVGTDwT0Y9i3yxUlTe2KMen4J554sFCPPZko5CFyZJGhM96WkeaJk53NFss5odkM1JxmSWbJWhiDh7VHyWcFYwja21FQLJnV6aDEZjMz5GfAFmwZb21UmVfoNKnVuYEaIwUl72AK263ulDVNYadnDnL/9OfBStBo8Hp1F7GmCMyqu/NkYqbZpUl4zdkv5yPFkC4LvTIk7DokMIptNMa0jxAx4pb0yZSmDxEWQHngOxMvUqTkYsOuxsy/hJ6NQZ0aOGrJdPdwPmatqoq71SKvOmWTsxoHdx6ph+jBOwIzEyYDEGi9npFuOQ1mZ/YaubNK0YeRQ2Gcy3Yc1JMxuzj5Cn1NsosDppJOefeSReaLeJg1hgp1m2IMB0GmGiAPYHMlNHJd0sRxzSwMQMHSMc19QBHTXYZAPbYBzzAkJMApLTuQk8GXpAph6TrHyzBc8Am0Aim1IhWaVmGk6RGZcmQUhGDsw9JgQAfYKNBlqMeQ/1pDzwvHiLuH1r6EPPmFJdNp90mY4jtBnn+tR/bO5tDGy7fmUgy2fYps4DRu8sPcfuS5kPOKDQj6XkC+Up6oSTJjQI5jnmZ/+nTUat0MwxfjEyZcs07VaP2AtaDpBHI92A71XHqJT5ncasyoMtGW3bgArNUqLcyEEx2u5x5A6W8th/wDuXnTqvZ5WxcLo4+kZbTWx02lO0Fg2msqrCdHLPLinerVHYuqze50i7hgc0mqTy48eCFNESfmmKENY9QXmkZpp48EgD3pqSSsY1JsmoyGpBlcLPXYJAD2IWeaUB4oWYeYLNjoyNP5qfZNDnzTrK01SQ5k1MQ5O1QjKkIxrlZDykzPYoGf5Kb8FEzAzVuNl7LagGT3qQjHmo/DeimTwXoFplIJ4DQIGns8F91adUgDyZeNCg8lGaTUlBzPelghzeHNOgYp5lgo6HNFgaFA0R4JiGZJqPeNSDwbFGvBgSpMkcBp0DQiezRqBQHilm9sQWaVrI1AeSe80lk96U8hc960yFlhnsUxDewVfpp7FOs8FHLK2NIBJTzJ5kow3iBOxpO4Fm1bVgZDYuMEuMebSWajqYC9sFBGe9GyTUafzU7NQpkM10zZFMkuPwQ9beEIZ7lKe9szP6rvlGoo+CmJm81DzNgL0GIwF400Zpp496RrbFskpDzyFM1zxoQzVgLRTKCZPNGspKoCwXLg4LkpkeCkIGQSAxUYBqQhvYGvC1ToNDt4yOPuUhM3tGqvSqqLIY5Iiq1v0Npb1vwVuVQrtMQlGq+j69JJ53JRTJrTQSzJ4CigNRoGiAeWOjJIDXZoUD+pO5qR5GsvKYh8FX2clYIXyl8qmzFSQz2Jruv8AkmjeQ4Goy37FSTzzxUU8zuUrhmSaeZFPNM2RDml5pUnBBGe9aZ7ubUnTeQrxpRmhzP6lZGjwGpKBM34qCN5LhyfVSZJYKaLTTzAFK+Cq9Hk5iCntf6lxMs9iCMhSDNDmf1JGazh0k0KZ706fBCGBKs0BAPLtZD7gBNG9gCsBZzMPJRk+ZmSEkySQpvLfEg+HNScN4QUKDyKZkoyBPaw4JAPDmo/Wz8lwPLNQWOMadePAVGQ5KIeeHS5KOp
