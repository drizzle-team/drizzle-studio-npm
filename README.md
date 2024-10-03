# Drizzle Studio NPM Package 📦
If you're looking for a Drizzle Studio NPM package to install into your product - you're in the right place!
<br>

![image](https://github.com/drizzle-team/drizzle-studio-npm/assets/4045375/9ac739e0-ec3d-4902-840d-abb3b71e3f17)

  
Drizzle Studio is a web based modern database browser which comes in a form of:
  1. [Drizzle Studio for Local Development](https://orm.drizzle.team/drizzle-studio/overview) for your Drizzle ORM projects
  2. [Drizzle Studio Chrome Extension](https://driz.link/extension) which lets you browse PlanetScale, Cloudflare D1, Vercel Postgres and AWS Data API directly in their native consoles
  3. Drizzle Studio Gateway(work in progress) is a deployable Dockerized version of Studio on steroids, which you can put into your infrastructure and connect privately to your databases
  4. Drizzle Studio Component <- you're here
  

<br>

`Drizzle Studio embeddable Component` - is a pre-bundled framework agnostic web component of Drizzle Studio which you can embed into your UI(React/Vue/Svelte/VanillaJS/whatever). That is an extremely powerful UI element that can elevate your offering if you provide Database as a SaaS or a data centric SaaS solutions based on SQL or for private non-customer facing in-house usage.  
  
**Database platforms using Drizzle Studio:**
- [Turso](https://turso.tech), our first customers since Oct 2023!
- [Neon](https://neon.tech), [launch post](https://neon.tech/docs/changelog/2024-05-24)
- [Hydra](https://www.hydra.so/), undergoing integration

**Data Centric platforms using Drizzle Studio:**
- [Nuxt Hub](https://hub.nuxt.com), Sébastien Chopin's [launch post](https://x.com/Atinux/status/1768663789832929520)
- [Deco](https://deco.cx/), undergoing integration

<br>

We also have a set of companies using embeddable Drizzle Studio components for internal use cases

### Customisations
Drizzle Studio is highly customisable and we have an advanced [theming platform](https://drizzle.studio), we have an opt-in SQL query runner and we can add various partner-specific customizations on demand 👍  

Drizzle Studio has an **opt-in SQL query runner**:
![image](https://github.com/drizzle-team/drizzle-studio-npm/assets/4045375/6e179d12-5026-4b9f-8e52-f4aa8ae8e883)

in-place editable **JSON** support:
<img width="1447" alt="Screenshot 2024-06-12 at 14 39 16" src="https://github.com/drizzle-team/drizzle-studio-npm/assets/4045375/f91bd27b-c868-4010-8309-465876529e81">

**Advanced filtering** and lots of other useful stuff:
![image](https://github.com/drizzle-team/drizzle-studio-npm/assets/4045375/8bbc4146-e66d-4231-9240-253335002032)

### Integration
We distribute Drizzle Studio as a private npm package and here's how in-code integration looks like:
```ts
import type { DrizzleStudioRef } from '@drizzle-team/your-company-studio';
import StudioScript from '@drizzle-team/your-company-studio?raw';


const lightCssVariables = {
  "--background": "#ffffff",
  ...
};
const darkCssVariables = { ... };


function App() {
  // create a ref to the drizzle-studio component
  const studioRef = useRef<DrizzleStudioRef>(null);
  const [theme, setTheme] = useState<'light' | 'dark'>('light');

  return (
    <div style={{
      height: '100%',
      width: '100%',
      display: 'flex',
      flexDirection: 'column',
    }}>
      <button onClick={() => setTheme(theme === 'light' ? 'dark' : 'light')}>
        Change theme
      </ button>
      <drizzle-studio
        ref={studioRef}
        css-variables={JSON.stringify(theme === 'light' ? lightCssVariables : darkCssVariables)} // styling 
        title="Drizzle Studio"
        style={{
          flexGrow: 1,
          minHeight: 0,
        }}
      />
    </div>
  )
}

export default App
```

### Pricing
Pricing depends on the size of you platform and if it's going to be customer facing or internal, and we do have reduced pricing for Sponsors if you you're interested in supporting our OSS venue and have brand awareness and a relevant traffic to your offering!
  
Feel free to reach out on [𝕏](https://x.com/drizzleorm), in our [Discord](https://driz.link/discord) or via [mail](mailto:aleksandrblokh@gmail.com)!
