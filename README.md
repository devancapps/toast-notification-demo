# Toast Notification System

## Overview
A lightweight, customizable toast notification system for web applications. This system provides non-intrusive, temporary notifications that slide in from the right side of the screen and automatically disappear after a set duration.

![Toast Demo Types](https://i.imgur.com/placeholder.jpg)

## Features
- 🎨 Three notification types: Success, Error, and Info
- ⚡ Smooth slide-in and fade-out animations
- 📱 Responsive design
- 🎯 Customizable duration and styling
- 🔧 Easy integration
- 📦 No external dependencies (except Tailwind CSS)
- 🖼️ Built-in icons for different message types
- 📚 Stack multiple notifications

## Installation

1. Include Tailwind CSS in your project:
```html
<link href="https://cdnjs.cloudflare.com/ajax/libs/tailwindcss/2.2.19/tailwind.min.css" rel="stylesheet">
```

2. Copy the CSS into your stylesheet:
```css
.toast-container {
    position: fixed;
    bottom: 20px;
    right: 20px;
    z-index: 1000;
}

.toast {
    transform: translateX(100%);
    animation: slideIn 0.3s forwards, fadeOut 0.3s 2.7s forwards;
}

@keyframes slideIn {
    to {
        transform: translateX(0);
    }
}

@keyframes fadeOut {
    to {
        opacity: 0;
    }
}
```

3. Add the toast container to your HTML:
```html
<div class="toast-container"></div>
```

## Usage

### Basic Usage
```javascript
// Show a success toast
showToast('Operation successful!', 'success');

// Show an error toast
showToast('Something went wrong!', 'error');

// Show an info toast
showToast('New message received', 'info');
```

### Integration Example
```html
<button onclick="showToast('Item added to cart!', 'success')" 
        class="bg-green-500 text-white p-2 rounded">
    Add to Cart
</button>
```

## API Reference

### showToast(message, type)
Shows a toast notification.

Parameters:
- `message` (string): The message to display
- `type` (string, optional): Type of toast - 'success', 'error', or 'info'. Defaults to 'success'

```javascript
showToast('Hello World!', 'success');
```

### Helper Functions

#### getToastColor(type)
Returns the appropriate Tailwind CSS classes for the toast background color.

#### getToastIcon(type)
Returns the SVG icon markup for the specified toast type.

## Customization

### Modifying Duration
Change the timeout duration in the showToast function:
```javascript
setTimeout(() => {
    toast.remove();
}, 3000); // Change 3000 to your desired duration in milliseconds
```

### Changing Position
Modify the toast-container CSS:
```css
.toast-container {
    position: fixed;
    /* Change position by modifying these properties */
    top: 20px;     /* for top positioning */
    bottom: 20px;  /* for bottom positioning */
    left: 20px;    /* for left positioning */
    right: 20px;   /* for right positioning */
    z-index: 1000;
}
```

### Custom Styling
Add your own classes to the toast element:
```javascript
toast.className = `toast mb-4 p-4 rounded-lg shadow-lg flex items-center 
    ${getToastColor(type)} your-custom-class`;
```

## Browser Support
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Opera (latest)

## Performance Considerations
- Toasts are automatically removed from the DOM after animation
- SVG icons are inline for better performance
- Animations use GPU acceleration where possible
- DOM operations are minimized

## Best Practices
1. Keep messages concise and clear
2. Use appropriate toast types for different messages
3. Don't show too many toasts simultaneously
4. Consider mobile viewers when writing messages
5. Ensure sufficient contrast for accessibility

## Contributing
Feel free to submit issues and enhancement requests!

## License
MIT License - feel free to use in your projects

## TODO
- [ ] Add click to dismiss
- [ ] Add progress bar
- [ ] Add custom duration option
- [ ] Add pause on hover
- [ ] Add accessibility improvements
- [ ] Add RTL support
- [ ] Add custom themes
- [ ] Add animation customization

## Credits
- Icons based on Heroicons
- Styling inspired by Tailwind CSS
- Animation techniques from modern web practices

## Support
For support, please open an issue in the repository.

---

Created by Devan Capps