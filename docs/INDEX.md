# Documentation

# Table of Contents

- [Add specialization to vehicle type](#add-specialization-to-vehicle-type)
- [Vehicle XML](#vehicle-xml)
- [Processor types](#processor-types)
  - [Split Processor](#split-processor)
  - [Blend Processor](#blend-processor)

Documentation files:
- 🗎 [XSD validation schema](./schema/materialProcessor.xsd)
- 🗎 [HTML schema](./schema/materialProcessor.html)

## Add specialization to vehicle type

```xml
<?xml version="1.0" encoding="utf-8" standalone="no"?>
<modDesc version="...">
    ...
    <vehicleTypes>
        <!-- Extend parent type, can be anything -->
        <type name="..." parent="..." className="..." filename="...">
            ...
            <!-- Add materialProcesor as last entry to type -->
            <specialization name="FS22_1_MaterialProcessor.materialProcessor" />
        </type>
    </vehicleTypes>
    ...
</modDesc>
```

## Vehicle XML
```xml
<?xml version="1.0" encoding="utf-8" standalone="no"?>
<vehicle ...>
    ...
    <materialProcessor type="...">
        ...
    </materialProcessor>
    ...
</vehicle>
```

## Processor types

### Split Processor

```xml
<?xml version="1.0" encoding="utf-8" standalone="no"?>
<vehicle>
    <materialProcessor type="split">
        ...
    </materialProcessor>
</vehicle>
```

Process one single input fillUnit and split the value into multiple output fillUnits. This specialization supports multiple discharge nodes vs base game which only supports 1.

For implementing a Split Processor [read more here](./PROCESSOR_SPLIT.md).


## Blend Processor

```xml
<?xml version="1.0" encoding="utf-8" standalone="no"?>
<vehicle>
    <materialProcessor type="blend">
        ...
    </materialProcessor>
</vehicle>
```

Process multiple input fillUnits into one output fillUnit.

For implementing a Blend Processor [read more here](./PROCESSOR_BLEND.md).