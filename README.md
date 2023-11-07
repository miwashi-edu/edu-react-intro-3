# edu-react-intro-3

## Instructions

```bash
cd ~
cd ws
cd react-app
npx storybook init
```

## Remove Demo

```bash
rm ./src/stories/*.jsx
rm ./src/stories/*.css
rm ./src/stories/*.js
rm ./src/stories/*.mdx
```

## Add new component

```bash
mkdir -p ./src/components/Gomoku
touch ./src/components/Gomoku/Gomoku.jsx
touch ./src/components/Gomoku/gomoku.css
touch ./src/components/Gomoku/index.js
touch ./src/stories/Gomoku.stories.js
```

## ./.storybook/main.js

```
cat > ./.storybook/main.js  << EOF
/** @type { import('@storybook/react-webpack5').StorybookConfig } */
const config = {
  stories: [
    "../src/stories/**/*.mdx",
    "../src/stories/**/*.stories.@(js|jsx|mjs|ts|tsx)",
  ],
  addons: [
    "@storybook/addon-links",
    "@storybook/addon-essentials",
    "@storybook/addon-onboarding",
    "@storybook/addon-interactions",
  ],
  framework: {
    name: "@storybook/react-webpack5",
    options: {},
  },
  docs: {
    autodocs: "tag",
  },
};
export default config;
EOF
```

## ./src/stories/Configure.mdx

```bash
cat > ./src/stories/Configure.mdx << 'EOF'
import { Meta, Story, Preview } from '@storybook/addon-docs/blocks';

<Meta title="Your Component Title" />

# Your Component Title

An introduction to your component.

<Preview>
  <Story name="Basic">
    
  </Story>
</Preview>
EOF
```

## ./src/components/Gomoku/index.js

```bash
cat > ./src/components/Gomoku/index.js << EOF
//for bundling
export {default as Gomoku} from "./Gomoku"

//for storybook
export {default} from "./Gomoku"

EOF
```

## ./src/components/Gomoku/Gomoku.jsx

```bash
cat > ./src/components/Gomoku/Gomoku.jsx << EOF
import React, { useEffect } from 'react';
import './gomoku.css';

const Gomoku = (props) => {
  useEffect(() => {
    console.log('Component mounted or updated');
  });

  return (
    <div>
      <h1>Gomoku</h1>
    </div>
  );
};

export default Gomoku;
EOF
```




