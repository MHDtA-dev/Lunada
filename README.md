# Lunada

![Logo](logo.JPG)

## Lunada - Simple cross-platform one header C++ library for serializing and saving data

## Brief description:

Suppose you have a structure:

```cpp

struct MyData {
  int a, b, c;
  float d, e, f;
  bool myBool;
  std::string str;
  ...
}

```

And it's instance:

```MyData data;```

You can set values in it:

```cpp
data.a = 1;
data.b = 2;
data.myBool = true;
str = "Hello!";
...
```

With Lunada, you can easily serialize this structure and save it to a file:

```cpp
Lunada::SerializeStruct<MyData>(data, "data_serialized.lunada");
```

After that, you can also easily read this structure from the file back:

```cpp
MyData dataFromFile;
Lunada::DeserializeStruct<MyData>(dataFromFile, "data_serialized.lunada");
```

**Note:** Do not use data types with dynamic size in your struct, such as std::vector, std::unordered_map etc. since Lunada will not save them, and the rest of the data will be saved with errors. To save such types of data, refer to the methods below:



