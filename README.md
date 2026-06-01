# Resolver Extras

## Artifacts:

### `conditional-a`

An example artifact that **optionally** depends on `conditional-b`.

### `conditional-b`

An example artifact that **has activationCondition** in form of `artifactPresent(org.slf4j:slf4j-api)`.

### `consumer-a`

An example artifact that declares **capability consumption** on label `slf4j-backend`.

### `provider-a`

An example artifact that declares **capability provider** on label `slf4j-backend`.

## Examples

### `capability`

* Case1: `mvn package` build FAILS - consumption not satisfied.
* Case2: `mvn package -P satisfy`, here profile pulls in `provider-a` and consumption is satisfied, build SUCCEEDS.
* Case3: `mvn package -P discover`, here profile provides instructions how to discover provider, build SUCCEEDS.

### `conditional`

* Case1: `mvn toolbox:tree` dependency `slf4j-simple` is absent from tree (condition is not satisfied).
* Case2: `mvn toolbox:tree -P satisfy`, dependency `slf4j-simple` is present in tree (condition is satisfied).
