# json_serializable_example

A new Flutter application.

## Add Dependencies

```yaml
dependencies:
  json_annotation: ^3.0.1

dev_dependencies:
  build_runner: ^1.10.0
  json_serializable: ^3.4.0
```

## Create Model

```dart
import 'package:json_annotation/json_annotation.dart';

part 'user.g.dart';

@JsonSerializable()
class User {
  String name;
  String email;

  User(this.name, this.email);

  factory User.fromJson(Map<String, dynamic> json) => _$UserFromJson(json);

  Map<String, dynamic> toJson() => _$UserToJson(this);
}
```

## Generate

```bash
flutter pub run build_runner build
```

- OR

```bash
make gen
```