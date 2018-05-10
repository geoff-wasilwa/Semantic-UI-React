 * WE DO NOT support `partAs`, because: leads to `partProps`, ...
 * WE DO NOT support `renderPart`, because: we can just use `part={}` and support functions as shorthand
 * WE DO NOT support arrays for `as` or (also: `part={}`), arrays are not considered shorthand primitives
 * ^^ Can still be used for higher-level props, such as `<Modal actions={[]} />`, because this is handled @ component level

## Principles
* "Just works" out of the box
* Intuitive :: should be able to work w/ lib w/o consulting docs
* Global Traits
* Pragmatic Design Language > whatever SUI does now (come up w/ name)
* Consistency

## THE BIBLE
* Trait prop names will never collide
* All component parts have a shorthand prop of the same name
* ^ ex issue: <Button icon /> <Header icon />
* ^ shorthand props may become render props, shorthand factories may accept functions
* All components should have a unique, human-readable classname
* ^ use atomic classes, we can go backwards (html w/ BEM -> CSS in JS) if needed
* All component parts need to be theme-able

## Good Parts
* Auto controlled components
* "as" support (good idea :: difficult implementation)
* Shorthand syntax ^ fits w/ "just works" :: principle of least surprise, do the right thing (but w/o magic)
* Integrated styling (e.g. attached) :: explore behaviors?? :: aggregate via composition

## Bad Parts
* External CSS dependency, barrier to first run
* Difficult to theme
* Tight coupling between markup and CSS, difficult to compose/wrap components
* Inconsistent support for "traits"
* Undiscoverable "cute" modifiers, hard to programmatically use ("big" "huge", etc.)
* Organization of components (addons, views, etc.)

## Like from Other Libraries
* Ant atom -> molecule -> ... idea :: core building block

## Disike from Other Libraries
* MUI: abuse of `children` prop, non-idiomatic React
* MUI: documentation where API and demo are split. Demos should not rely on external/custom code.

## Start/Continue
* Manifesto, guiding principles
* Human documentation, more about ideas and principles than strictly API reference
* Human release notes (not mutually exclusive w/ auto generated changes) + upgrade guide
* Themer tool + prop knobs in sandbox
* Versioned docs
* Step-by-step intro to concepts :: rotating components w/ props

## Brainbox
* Auto wrapping of children, escape hatch w/ render functions as children?
* Avoid internal cloning of elements to modify them (e.g. shorthand factories + triggers) :: Not all cloned userland elements can be guaranteed to spread props through
* ^^ Need to be able to be consistent regardless of userland
* EVERY COMPONENT SHOULD TAKE A `theme` PROP!!!! [david suggestion]

## STYLE BIBLE :: STYBLE
* Only layouts can implement whitespace padding
* ^ does this mean that we never use margins? any margin could be a parent layout's padding

## Action Items
1) Get <Layout /> and <List /> working in SUIR v2 branch
2) Move docs to CSS in JS
3) Default component sandbox needs to have a theme switcher
4) Design specs for Image, Icon, Label, and Avatar
5) Create <Image />
6) Create <Icon />
7) Create <Label />
8) Create <Avatar /> w/ Image, Icon, and Label

## Theming
* [ ] Formalize contract
* [ ] Enables theme switcher
* [ ] Formalize component vars
* [ ] Enables iterate + show var controls in each example

## ALWAYS SAY WHY BEHIND BIBLE RULES
