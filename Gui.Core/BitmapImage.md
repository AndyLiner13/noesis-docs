# BitmapImage Class

## namespace [Noesis](https://www.noesisengine.com/docs/Gui.Core._ClassHierarchy.html#noesis-namespace) | [MSDN](https://msdn.microsoft.com/en-us/library/system.windows.media.imaging.bitmapimage.aspx)

Provides a [BitmapSource](https://www.noesisengine.com/docs/Gui.Core._BitmapSource.html) created from an image file located at the specifed [Uri](https://www.noesisengine.com/docs/Gui.Providers._Uri.html).

## Inheritance Hierarchy

- [DispatcherObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DispatcherObject.html)
- [DependencyObject](https://www.noesisengine.com/docs/Gui.DependencySystem._DependencyObject.html)
- [Freezable](https://www.noesisengine.com/docs/Gui.DependencySystem._Freezable.html)
- [Animatable](https://www.noesisengine.com/docs/Gui.Core._Animatable.html)
- [ImageSource](https://www.noesisengine.com/docs/Gui.Core._ImageSource.html)
- [BitmapSource](https://www.noesisengine.com/docs/Gui.Core._BitmapSource.html)
- BitmapImage

## Properties

### From BitmapSource

| Property | Description |
|----------|-------------|
| DpiX | Horizontal DPI of the bitmap |
| DpiY | Vertical DPI of the bitmap |
| Format | Gets bitmap format |
| PixelHeight | Height, in pixels, of the bitmap |
| PixelWidth | Width, in pixels, of the bitmap |

### From ImageSource

| Property | Description |
|----------|-------------|
| Height | Gets the height of the image in measure units (96ths of an inch) |
| Width | Gets the width of the image in measure units (96ths of an inch) |

### From Freezable

| Property | Description |
|----------|-------------|
| CanFreeze | Gets a value that indicates whether the object can be made unmodifiable. |
| IsFrozen | Gets a value that indicates whether the object is currently modifiable. |

### From DispatcherObject

| Property | Description |
|----------|-------------|
| ThreadId | Gets the thread this DispatcherObject is associated with. Returns NoThreadId when this object is not attached to any thread. |

### Own Properties

| Property | Description |
|----------|-------------|
| UriSource | Gets or sets the image Uri source |

## Attached Properties

BitmapImage has no attached properties

## Methods

### From BitmapSource

| Method | Description |
|--------|-------------|
| CopyPixels(buffer, bufferSize, stride, offset) | Copies the bitmap pixel data into an array of pixels with the specified stride, starting at the specified offset |
| Create(pixelWidth, pixelHeight, dpiX, dpiY, buffer, stride, format) | Creates a new BitmapSource from an array of pixels that are stored in memory |

### From Freezable

| Method | Description |
|--------|-------------|
| Clone() | Creates a modifiable clone of the Freezable, making deep copies of the object's values. When copying the object's dependency properties, this method copies expressions (which might no longer resolve) but not animations or their current values. The cloned Freezable::IsFrozen property is false even if the source's IsFrozen property is true. |
| CloneCurrentValue() | Creates a modifiable clone (deep copy) of the Freezable using its current values. The cloned object's IsFrozen property is false even if the source's IsFrozen property is true. |
| Freeze() | Makes the current object unmodifiable and sets its IsFrozen property to true. |
| GetAsFrozen() | Creates a frozen copy of the Freezable, using base (non-animated) property values. Because the copy is frozen, any frozen sub-objects are copied by reference. The copy's IsFrozen property is set to true. Throws if the Freezable cannot be frozen because it contains expressions or animated properties. |
| GetCurrentValueAsFrozen() | Creates a frozen copy of the Freezable using current property values. Because the copy is frozen, any frozen sub-objects are copied by reference. The copy's IsFrozen property is set to true. |

### From DependencyObject

| Method | Description |
|--------|-------------|
| ClearAnimation(dp) | Clears the animation value of a property |
| ClearLocalValue(dp) | Clears the local value of a property The property to be cleared is specified by a DependencyProperty identifier |
| CoerceValue(dp) | Coerces and validates the effective property value |
| DependencyPropertyChanged() | Returns the PropertyChanged event |
| Destroyed() | Destroyed delegate is raised when object is going to be destroyed |
| GetBaseValue(dp) | Returns the base value without animation nor coerce (this never returns Expression like GetLocalValue) |
| GetExpression(dp) | Gets the expression, if any, used to evaluate the specified property value |
| GetLocalValue(dp) | Returns the local value of a dependency property, if it exists |
| GetValue(dp) | Returns the current effective value of a dependency property on this instance of a DependencyObject |
| GetValueObject(dp) | Returns the current effective value of a dependency property on this instance of a DependencyObject as a boxed value |
| GetValueProvider(dp) | Gets the provider that returns the effective value for the specified dependency property |
| HasAnimatedProperties() | Returns true if there is any animated property |
| InvalidateProperty(dp, priority) | Re-evaluates the effective value for the specified dependency property if necessary If null is passed, a full re-evaluation could be needed |
| IsCached(dp, provider) | Returns if the value is stored in the cache. If true, the priority is returned in the provider field |
| IsSealed() | Gets a value that indicates whether this instance is currently sealed (read-only) |
| SetAnimation(dp, value) | Sets the animated value of a property |
| SetCurrentValue(dp, value) | Sets the current value of a dependency property. The current value is set on the coerce field, without modifying source or animated value |
| SetCurrentValueObject(dp, value) | Sets the current value of a dependency property using a boxed value |
| SetExpression(dp, expression) | Sets the expression to be evaluated dynamically to obtain the value of the property |
| SetValue(dp, value) | Sets the local value of a dependency property |
| SetValueObject(dp, value) | Sets the local value (boxed) of a dependency property |

### From DispatcherObject

| Method | Description |
|--------|-------------|
| CheckAccess() | Determines whether the calling thread has access to this DispatcherObject |
| VerifyAccess() | Enforces that the calling thread has access to this DispatcherObject |

## Events

BitmapImage has no events