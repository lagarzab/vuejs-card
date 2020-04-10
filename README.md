# Card
A simple card component used to present a concise piece of site content, an image, and/or text. A simple hover effect is applied automatically.
An rgba(169, 169, 169, .5) is either applied or 'removed' when the effect is in place (on :hover by default).

## Usage
The card component exports only a card component.

### `card` Component
`card` has 3 slots available for placement of your information, buttons, logos, images and text.
- `header`: Displayed at the top. Flex item, minimal size and not shown if not filled.
- `footer`: Displayed at the bottom. Flex item, minimal size and not shown if not filled.
- `default`: Displayed in between header and footer. Flex item, stretches the remainder of the height of container that isn't occupied by the header and/or footer slots.

There are props available for interaction and styling:

- `link`: prop to allow the card to be clickable.
- `height`/`width`: props allow you to change the size of the component (defaults to 350px/250px)
- `headerStyle`, `contentStyle`, `footerStyle`: Allow you to pass css to each slot, if you need specific styling applied to them.
- `blurReverse`: sending true will 'blur' place an rgba(169, 169, 169, .5) by default, and when :hover is in effect the rgba is removed (this defaults to false).
