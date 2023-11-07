# edu-react-intro-3

## ./src/components/Gomoku/Gomoku.jsx

```bash
cat > ./src/components/Gomoku/Gomoku.jsx << EOF
// Gomoku.js
import React, { useEffect } from 'react';
import PropTypes from 'prop-types';
import './gomoku.css';

const Gomoku = ({ trigger }) => {
  useEffect(() => {
    console.log('Effect triggered by:', trigger);
  }, [trigger]);

  return (
    <div>
      <h1>Gomoku</h1>
    </div>
  );
};

Gomoku.propTypes = {
  trigger: PropTypes.string,
};

Gomoku.defaultProps = {
  trigger: '',
};

export default Gomoku;
EOF
```

## ./src/stories/Gomoku.stories.js

```bash
cat > ./src/stories/Gomoku.stories.js << EOF
// Gomoku.stories.js
import React from 'react';
import Gomoku from "../components/Gomoku";

export default {
    title: 'Gomoku/Gomoku',
    component: Gomoku,
    parameters: { layout: 'centered' },
    argTypes: {
        trigger: {
            control: 'text',
            description: 'A string to trigger the useEffect',
        },
    },
};

const Template = (args) => <Gomoku {...args} />;

export const TriggerEffect = Template.bind({});
TriggerEffect.args = {
    trigger: 'Initial trigger',
};
EOF
```



