# on_state_control_changed extendend

## Why
This code aims to minimize the usage of large if, else_if, else chains in on_state_control_changed.
This makes your code more pretty and if you use a lot of on_state_control_changed more efficient.

## How does this work?
This code uses meta_effect to target scripted_effects in a fashion of TAG_on_lose_state, TAG_on_gain_state, STATEID_on_change_controller which directly determine who took control of a state, who lost control of the state, and what state that was.
Rather than if chaining condition of ROOT = { tag = XXX } instead XXX_on_gain_state scripted effect will be called. Within XXX_on_gain_state you can now assume that the New controller is tag XXX.

## How do I use this?
Import the common/on_actions/state_ext_on_actions.txt into your own on_actions.

Don't forget to set the right flags!
Don't forget to implement the scripted_effects.

And it'll take care of itself afterwards.







