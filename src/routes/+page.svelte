<script>
    let birthDate = $state('2006-09-17');
    let age = $derived.by(() => {
    const today = new Date();
    const birth = new Date(birthDate);
    
    let calculatedAge = today.getFullYear() - birth.getFullYear();
    const monthDiff = today.getMonth() - birth.getMonth();
    
    if (monthDiff < 0 || (monthDiff === 0 && today.getDate() < birth.getDate())) {
      calculatedAge--;
    }
    
    return calculatedAge;
  });
</script>

<main>
  <section aria-labelledby="intro-title">
    <header>
      <p class="eyebrow">Sobre mim</p>
      <h1 id="intro-title">Olá, meu nome é Felipe Bonfim Anthiuk</h1>
    </header>

    <p>
      Tenho {age} anos e sou um estudante de Ciência da Computação (UNINTER). Sou apaixonado por tecnologia e programação,
      e estou sempre em busca de aprender coisas novas e aprimorar minhas habilidades.
    </p>

    <p>
      Aqui, quero compartilhar meus projetos, minha evolução, experiências e conhecimentos com a comunidade.
      Sinta-se à vontade para explorar meu portfólio e entrar em contato caso tenha interesse em colaborar ou
      discutir ideias.
    </p>
  </section>
</main>

<style>
  main {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    min-height: 100vh;
    padding: 3rem 1.5rem;
    box-sizing: border-box;
    background-color: var(--color-ink);
    background-image: linear-gradient(
      135deg,
      color-mix(in srgb, var(--color-night) 85%, var(--color-ink)),
      var(--color-ink) 55%,
      color-mix(in srgb, var(--color-sky) 14%, var(--color-ink))
    );
    color: var(--color-cloud);
  }

  section {
    width: 100%;
    max-width: 800px;
    padding: clamp(2rem, 6vw, 4.5rem);
    box-sizing: border-box;
    border: 1px solid var(--color-mist);
    border-top: 0.35rem solid var(--color-lime);
    border-right: 0.35rem solid var(--color-sky);
    border-radius: 0.5rem;
    background-color: var(--color-night);
    box-shadow: 0 1.5rem 3rem color-mix(in srgb, var(--color-night) 22%, transparent);
  }

  header {
    margin-bottom: 2rem;
  }

  .eyebrow {
    margin: 0 0 0.75rem;
    color: var(--color-lime);
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 0.18em;
    text-transform: uppercase;
  }

  h1 {
    max-width: 14ch;
    margin: 0;
    color: var(--color-cloud);
    font-family: Georgia, serif;
    font-size: clamp(2.25rem, 6vw, 4.5rem);
    line-height: 0.98;
    letter-spacing: 0;
  }

  p {
    max-width: 65ch;
    font-size: 1.125rem;
    line-height: 1.7;
    margin-bottom: 1rem;
    color: var(--color-mist);
  }

  p:last-child {
    margin-bottom: 0;
  }

  @media (max-width: 480px) {
    main {
      padding: 1rem;
    }

    section {
      border-right-width: 0.2rem;
    }

    h1 {
      font-size: 2.5rem;
    }

    p {
      font-size: 1rem;
    }
  }
</style>