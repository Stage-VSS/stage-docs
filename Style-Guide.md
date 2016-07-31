# Style Guide

Maintaining a consistent coding conventions helps keep the Stage codebase readable and maintainable. This style guide has been created to guide writing code for the project.

## Guidelines

### Naming convention
- Class names are UpperCamelCase

  ```matlab
  classdef MyAwesomeClass
  ```

- Property names are lowerCamelCase

  ```matlab
  properties
      figureHandle
      settings
  end
  ```

- Function/method names are lowerCamelCase

  ```matlab
  function loadSettings(obj)
  ```

- Event names are UpperCamelCase

  ```matlab
  events
      SelectedParent
  end
  ```

- Local variables are lowerCamelCase

  ```matlab
  function v = getProperty(obj, name)
      descriptor = obj.getPropertyDescriptor(name);
      v = descriptor.value;
  end
  ```

### Whitespace
- Use 4 spaces instead of tabs (*MATLAB editors default*)
- Separate blocks (properties, events, functions, etc.) with a single blank line

  ```matlab
  properties
      someProperty
  end

  methods

      function delete(obj)
          obj.close();
      end

      function close(obj)
          obj.someProperty = [];
      end

  end
  ```

- Function/method declarations have no space between variables and surrounding brackets/parenthesis and no brackets unless required for multiple outputs

  ```matlab
  function myFunction()

  function out = myFunction(obj, in)

  function [out1, out2, out3] = myFunction(obj, in1, in2)
  ```

- Function/method calls match the spacing format of function declarations

  ```matlab
  myFunction()

  out = obj.myFunction(in)

  [out1, out2, out3] = obj.myFunction(in1, in2)
  ```

- Anonymous functions may have no space between input arguments

  ```matlab
  @(in1,in2)in1 + in2;
  ```

- Attributes have one space between keyword and attribute specification

  ```matlab
  properties (Constant, Abstract)

  methods (SetAccess = protected, Abstract)
  ```

- In general, add a space after commas. Vector/cell indices and anonymous function inputs are possible exceptions.

### Comments
- Class comments should immediately follow the classdef line and be indented

  ```matlab
  classdef MyAwesomeClass
      % The first sentence is important and should be a concise summary of the class. Now we include some more details and
      % it starts to flow on to the next line but it's always indented.
  ```

- Function/method comments should immediately follow the function line and be indented

  ```matlab
  function didSetPersistor(obj)
      % Override to perform actions after this protocol's persistor is set, e.g. assign property values based on
      % experiment entities. Note that persistor may be assigned as empty is there is no persistor.
  ```

- Prefer putting property comments on the same line as the property and vertically aligning them with other comments in the same property block

  ```matlab
  properties
      One     % First public property
      Two     % Second public property
  end
  ```

### Ordering
- Group methods by task (not alphabetically or randomly)
- Classes generally follow this block order:
  1. Events blocks
  1. Properties blocks
  1. Public methods
  1. Private methods
  1. Private functions

### Miscellaneous
- Avoid lines over 120 columns (set right-hand text limit to 120 columns in MATLAB preferences)
- Read [The Elements of MATLAB Style](http://www.cambridge.org/us/academic/subjects/computer-science/scientific-computing-scientific-software/elements-matlab-style)
