# Alert Component

A fully customizable alert component for React Native, supporting multiple variants, severities, animation, auto-dismissal, icons, actions, accessibility, and flexible styling options.

---

## Features
- Multiple alert variants: `filled`, `outlined`, `soft`, `solid`
- Severity levels: `success`, `info`, `warning`, `error`, `neutral`
- Configurable sizes: `small`, `medium`, `large`
- Auto-dismissal support
- Animation with `Animated` API
- Icon and close button support
- Supports theming and dynamic mode-based styling
- Flexible with custom styles and layout behavior

---

## Usage

```tsx
import { Alert, DismissibleAlert } from './Alert';

<Alert
  title="Success!"
  color="success"
  variant="filled"
  closable
  icon={<SuccessIcon />}
>
  Operation completed successfully.
</Alert>

<DismissibleAlert
  title="Timed Alert"
  autoDismiss
  autoDismissDuration={4000}
  color="info"
>
  This alert will disappear after 4 seconds.
</DismissibleAlert>
```

---

## Props

### `AlertProps`
| Prop               | Type                           | Default     | Description |
|--------------------|--------------------------------|-------------|-------------|
| `color`            | `'success' \| 'info' \| 'warning' \| 'error' \| 'neutral'` | `'info'` | Alert severity level |
| `variant`          | `'filled' \| 'outlined' \| 'soft' \| 'solid'`              | `'soft'` | Alert variant style |
| `size`             | `'small' \| 'medium' \| 'large'`                             | `'medium'` | Size of the alert |
| `title`            | `string`                       | `undefined` | Optional title |
| `children`         | `React.ReactNode`              | `required`  | Content/message of the alert |
| `closable`         | `boolean`                      | `false`     | Whether to show a close button |
| `icon`             | `React.ReactNode`              | `undefined` | Icon displayed at the start |
| `onClose`          | `() => void`                   | `undefined` | Triggered when the alert is closed |
| `prominent`        | `boolean`                      | `false`     | Adds a left border for emphasis |
| `style`            | `StyleProp<ViewStyle>`         | `undefined` | Custom container styles |
| `titleStyle`       | `StyleProp<TextStyle>`         | `undefined` | Custom title styles |
| `contentStyle`     | `StyleProp<TextStyle>`         | `undefined` | Custom content styles |
| `animate`          | `boolean`                      | `true`      | Animates the alert when mounted |
| `elevated`         | `boolean`                      | `false`     | Adds a subtle shadow |
| `action`           | `React.ReactNode`              | `undefined` | Action component displayed on the right |
| `fullWidth`        | `boolean`                      | `false`     | Makes the alert span full width |
| `borderRadius`     | `number`                       | theme-based | Overrides border radius |
| `testID`           | `string`                       | `undefined` | Test ID for e2e tests |

### `DismissibleAlertProps` (extends `AlertProps`)
| Prop                  | Type      | Default | Description |
|-----------------------|-----------|---------|-------------|
| `autoDismiss`         | `boolean` | `false` | Dismisses the alert automatically after duration |
| `autoDismissDuration` | `number`  | `6000`  | Duration in ms before dismissal |

---

## ⚙️ Animation
- Uses `Animated.View` for fade in/out transitions
- Controlled by the `animate` prop

---

## ♿ Accessibility
- Sets `accessibilityRole="alert"`
- Close button includes `accessibilityLabel="Close alert"`

---

##  Customization
You can override:
- Container, title, and content styles
- Border radius
- Actions, icons, and spacing
- Typography via size prop

---

## Testing
Use `testID` prop to target the alert in testing frameworks:
```tsx
<Alert testID="my-alert">Testable Alert</Alert>
```


