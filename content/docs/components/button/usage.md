## Import

```js
import { Button, ButtonGroup } from '@chakra-ui/react'
```

- **Button:** The button component with support for custom icons, spinners, etc.
- **ButtonGroup:** Used to group buttons whose actions are related, with an
  option to flush them together.

## Usage

```jsx
<Button colorScheme='blue'>Button</Button>
```

### Button Sizes

Use the `size` prop to change the size of the button. You can set the value to
`xs`, `sm`, `md`, or `lg`.

```jsx
<Stack spacing={4} direction='row' align='center'>
  <Button colorScheme='teal' size='xs'>
    Button
  </Button>
  <Button colorScheme='teal' size='sm'>
    Button
  </Button>
  <Button colorScheme='teal' size='md'>
    Button
  </Button>
  <Button colorScheme='teal' size='lg'>
    Button
  </Button>
</Stack>
```

### Button variants

Use the `variant` prop to change the visual style of the Button. You can set the
value to `solid`, `ghost`, `outline`, or `link`.

```jsx
<Stack direction='row' spacing={4} align='center'>
  <Button colorScheme='teal' variant='solid'>
    Button
  </Button>
  <Button colorScheme='teal' variant='outline'>
    Button
  </Button>
  <Button colorScheme='teal' variant='ghost'>
    Button
  </Button>
  <Button colorScheme='teal' variant='link'>
    Button
  </Button>
</Stack>
```

### Button Colors

Use the colorScheme prop to change the color scheme of the Button. You can set
the value to any of the color scales from your design system, like `whiteAlpha`,
`blackAlpha`, `gray`, `red`, `blue`, or your custom color scale.

```jsx
<Stack direction='column'>
  <Box
    display='flex'
    alignItems='center'
    justifyContent='center'
    width='100%'
    py={12}
    bgImage="url('https://bit.ly/2Z4KKcF')"
    bgPosition='center'
    bgRepeat='no-repeat'
    mb={2}
  >
    <ButtonGroup gap='4'>
      <Button colorScheme='whiteAlpha'>WhiteAlpha</Button>
      <Button colorScheme='blackAlpha'>BlackAlpha</Button>
    </ButtonGroup>
  </Box>

  <Wrap spacing={4}>
    <WrapItem>
      <Button colorScheme='gray'>Gray</Button>
    </WrapItem>
    <WrapItem>
      <Button colorScheme='red'>Red</Button>
    </WrapItem>
    <WrapItem>
      <Button colorScheme='orange'>Orange</Button>
    </WrapItem>
    <WrapItem>
      <Button colorScheme='yellow'>Yellow</Button>
    </WrapItem>
    <WrapItem>
      <Button colorScheme='green'>Green</Button>
    </WrapItem>
    <WrapItem>
      <Button colorScheme='teal'>Teal</Button>
    </WrapItem>
    <WrapItem>
      <Button colorScheme='blue'>Blue</Button>
    </WrapItem>
    <WrapItem>
      <Button colorScheme='cyan'>Cyan</Button>
    </WrapItem>
    <WrapItem>
      <Button colorScheme='purple'>Purple</Button>
    </WrapItem>
    <WrapItem>
      <Button colorScheme='pink'>Pink</Button>
    </WrapItem>
    <WrapItem>
      <Button colorScheme='linkedin'>Linkedin</Button>
    </WrapItem>
    <WrapItem>
      <Button colorScheme='facebook'>Facebook</Button>
    </WrapItem>
    <WrapItem>
      <Button colorScheme='messenger'>Messenger</Button>
    </WrapItem>
    <WrapItem>
      <Button colorScheme='whatsapp'>Whatsapp</Button>
    </WrapItem>
    <WrapItem>
      <Button colorScheme='twitter'>Twitter</Button>
    </WrapItem>
    <WrapItem>
      <Button colorScheme='telegram'>Telegram</Button>
    </WrapItem>
  </Wrap>
</Stack>
```

### Button with icon

You can add left and right icons to the Button component using the `leftIcon`
and `rightIcon` props respectively.

> Note: The `leftIcon` and `rightIcon` prop values should be react elements NOT
> strings.

```jsx
<Stack direction='row' spacing={4}>
  <Button leftIcon={<EmailIcon />} colorScheme='teal' variant='solid'>
    Email
  </Button>
  <Button rightIcon={<ArrowForwardIcon />} colorScheme='teal' variant='outline'>
    Call us
  </Button>
</Stack>
```

You can also use icons from popular libraries like
[react-icons](https://react-icons.github.io/react-icons/) and pass it into the
button.

```jsx
// import { MdBuild , MdCall } from "react-icons/md"

<Stack direction='row' spacing={4}>
  <Button leftIcon={<MdBuild />} colorScheme='pink' variant='solid'>
    Settings
  </Button>
  <Button rightIcon={<MdCall />} colorScheme='blue' variant='outline'>
    Call us
  </Button>
</Stack>
```

### Button loading state

Pass the `isLoading` prop to show its loading state. By default, the button will
show a spinner and leave the button's width unchanged.

You can also pass the `loadingText` prop to show a spinner and the loading text.

```jsx
<Stack direction='row' spacing={4}>
  <Button isLoading colorScheme='teal' variant='solid'>
    Email
  </Button>
  <Button
    isLoading
    loadingText='Submitting'
    colorScheme='teal'
    variant='outline'
  >
    Submit
  </Button>
</Stack>
```

You can change the spinner element to use custom loaders as per your design
requirements. Pass the `spinner` prop and set it to a custom react element.

```jsx
<Button
  isLoading
  colorScheme='blue'
  spinner={<BeatLoader size={8} color='white' />}
>
  Click me
</Button>
```

When a `loadingText` is present, you can change the placement of the spinner
element to either `start` or `end`. It is `start` by default.

```jsx
<Stack direction='row' spacing={4} align='center'>
  <Button
    isLoading
    loadingText='Loading'
    colorScheme='teal'
    variant='outline'
    spinnerPlacement='start'
  >
    Submit
  </Button>
  <Button
    isLoading
    loadingText='Loading'
    colorScheme='teal'
    variant='outline'
    spinnerPlacement='end'
  >
    Continue
  </Button>
</Stack>
```

### Social Buttons

We've included the colors for common social media platforms, and you can simply
use their buttons via the `colorScheme` prop.

```jsx
<HStack>
  <Button colorScheme='facebook' leftIcon={<FaFacebook />}>
    Facebook
  </Button>
  <Button colorScheme='twitter' leftIcon={<FaTwitter />}>
    Twitter
  </Button>
</HStack>
```

The Facebook and Twitter icons in the above example are available from
[`react-icons`](https://react-icons.netlify.com/#/) as `FaFacebook` and
`FaTwitter`, found in the `react-icons/fa` import.

### Grouping Buttons

You can use the `Stack` or `ButtonGroup` component to group buttons. When you
use the `ButtonGroup` component, it allows you to:

- Set the `size` and `variant` of all buttons within it.
- Add `spacing` between the buttons.
- Flush the buttons together by removing the border radius of their children as
  needed.

```jsx
<ButtonGroup variant='outline' spacing='6'>
  <Button colorScheme='blue'>Save</Button>
  <Button>Cancel</Button>
</ButtonGroup>
```

To flush the buttons, pass the `isAttached` prop.

```jsx
<ButtonGroup size='sm' isAttached variant='outline'>
  <Button>Save</Button>
  <IconButton aria-label='Add to friends' icon={<AddIcon />} />
</ButtonGroup>
```

## Accessibility

- Button has `role` of `button`.
- When Button has focus, <kbd>Space</kbd> or <kbd>Enter</kbd> activates it.

## Composition

All props you pass (`variant`, `colorScheme`, etc.) are converted to style
props. This means you can override any style of the Button via props.

```jsx
// The size prop affects the height of the button
// It can still be overridden by passing a custom height
<Button
  size='md'
  height='48px'
  width='200px'
  border='2px'
  borderColor='green.500'
>
  Button
</Button>
```

---

## Custom Button

In the event that you need to make your own custom button, you can leverage the
`Box` component. It provides the `hover`, `focus`, `active` and `disabled` style
props to style the button.

```jsx
// Button from facebook.com
<Box
  as='button'
  height='24px'
  lineHeight='1.2'
  transition='all 0.2s cubic-bezier(.08,.52,.52,1)'
  border='1px'
  px='8px'
  borderRadius='2px'
  fontSize='14px'
  fontWeight='semibold'
  bg='#f5f6f7'
  borderColor='#ccd0d5'
  color='#4b4f56'
  _hover={{ bg: '#ebedf0' }}
  _active={{
    bg: '#dddfe2',
    transform: 'scale(0.98)',
    borderColor: '#bec3c9',
  }}
  _focus={{
    boxShadow:
      '0 0 1px 2px rgba(88, 144, 255, .75), 0 1px 1px rgba(0, 0, 0, .15)',
  }}
>
  Join Group
</Box>
```
