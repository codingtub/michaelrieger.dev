<script lang="ts">
  import type { Skill } from "../_shared/types/skill";

  export let skills: Skill[];
</script>

<div class="skills-list">
  <div class="skills__list">
    {#each skills as skill}
      <article class="skill">
        <header class="skill__header">
          <img
            src={skill.icon}
            alt={skill.title + " icon"}
            class="skill__icon"
          />
          <h3 class="skill__title heading-s">{skill.title}</h3>
        </header>
        <div class="skill__content">
          <p class="skill__description text-s">{skill.description}</p>
          <h4 class="skill__subtitle heading-xs">{skill.skillsTitle}</h4>
          <ul class="skill__list">
            {#each skill.skillsList as skillItem}
              <li class="skill__item text-s">{skillItem}</li>
            {/each}
          </ul>
          <h4 class="skill__subtitle heading-xs">{skill.toolsTitle}</h4>
          <ul class="skill__list">
            {#each skill.toolsList as tool}
              <li class="skill__item text-s">{tool}</li>
            {/each}
          </ul>
        </div>
      </article>
    {/each}
  </div>
</div>

<style>
  .skills-list {
    padding: 0 var(--content-side-padding);
    margin-top: -10em;
    position: relative;
  }

  .skills__list {
    display: flex;
    flex-flow: column wrap;
    max-width: 1440px;
    min-height: 600px;

    margin: 0 auto;

    box-sizing: border-box;

    border-radius: var(--border-radius);
    box-shadow: var(--box-shadow);
  }

  .skill {
    display: flex;
    flex-flow: column wrap;
    align-items: center;

    min-height: 200px;

    box-sizing: border-box;
    padding: 3em 2em;

    text-align: center;
    background: var(--color-bg);
    border: 1px solid var(--color-border);
    border-radius: 0;
  }

  .skill:not(:first-child):not(:last-child) {
    border-radius: 0;
    border-top: none;
    border-bottom: none;
  }
  .skill:first-child {
    border-radius: var(--border-radius) var(--border-radius) 0 0;
    border-bottom: 1px solid var(--color-border);
  }

  .skill:last-child {
    border-radius: 0 0 var(--border-radius) var(--border-radius);
    border-top: 1px solid var(--color-border);
  }

  .skill__header {
    display: flex;
    flex-flow: column wrap;
    align-items: center;
  }

  .skill__icon {
    height: 50px;
    width: auto;
    margin-bottom: 2em;
  }

  .skill__title {
    margin-bottom: 1.5em;
    color: var(--color-text-dark);
  }

  .skill__content {
    color: var(--color-primary);
  }

  .skill__description {
    max-width: 52ch;
    margin-bottom: 2em;
    color: var(--color-text-skills);
  }

  .skill__subtitle {
    margin-bottom: 1em;
  }

  .skill__list {
    list-style: none;
    margin: 0;
    padding: 0;
  }

  .skill__list:not(:last-of-type) {
    margin-bottom: 3em;
  }

  .skill__item {
    color: var(--color-text-skills);
  }

  @media (min-width: 62em) {
    .skills__list {
      flex-flow: row nowrap;
      width: 100%;
    }

    .skill {
      flex: 1;
    }

    .skill:not(:first-child):not(:last-child) {
      border-radius: 0;
      border: 1px solid var(--color-border);
      border-left: none;
      border-right: none;
    }
    .skill:first-child {
      border-radius: var(--border-radius) 0 0 var(--border-radius);
    }
    .skill:last-child {
      border-radius: 0 var(--border-radius) var(--border-radius) 0;
    }

    .skill__description {
      max-width: 26ch;
      margin-bottom: 2em;
      color: var(--color-text-skills);
    }
  }
</style>
