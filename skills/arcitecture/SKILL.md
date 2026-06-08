---
name: architecture
description: Choose high-level design patterns when starting a new project or refactoring an existing one.
---

# Software architecture

This skill helps choose high-level design patterns when starting a new project or refactoring an existing one.

## Patterns

### Entity-action pattern

**When to use:** Use this pattern when a clear contract is desired.

**Key traits:** Flat or no heierarchy, public properties, well defined actions

When using this pattern start by identifying the entities. Entities are concrete objects with properties that can be acted on. List each entity and the properties it has.

Example:

Vehicle:
- occupancy
- height

Garage bay:
- vehicle
- maximum clearance

Garage:
- list of bays

Next identify the actions that will need to be taken on each entity or combination of entities to accomplish the task.

Example:

Park vehicle:
	- Vehicle
	- Garage

Check clearance:
	- Vehicle
	- Garage bay

Finally, implement this pattern with plain types for the entities and functions for the actions.

Example in Typescript:

```ts
interface Vehicle {
	occupancy: number
	height: number
}

interface GarageBay {
	vehicle: Vehicle
	maximumClearance: number
}

interface Garage {
	bays: GarageBay[]
}

function checkClearance(vehicle: Vehicle, bay: GarageBay): boolean {
	return vehicle.height < bay.maximumClearance;
}

function parkVehicle(vehicle: Vehicle, garage: Garage) {
	for (const bay of garage) {
		if (checkClearance(vehicle, bay)) {
			bay.vehicle = vehicle;
		}
	}
}
````

## Patterns to use sparingly

### Singleton pattern

**When to use:** Use when there is a cross-cutting concern, functionality that is needed by most or all modules.

**When not to use:** Do not use to make utilities classes. Avoid using if it will have side effects that would prevent unit tests from working consistently.

Singletons should have an idempotent getter that returns the single instance of the object. The single instance should be lazily initialized to avoid unnecessary memory usage.

Example in Typescript:

```ts
class ServiceClient {
	// ...
}

let _serviceClient = null;

function getServiceClient() {
	if (!_serviceClient) {
		_serviceClient = new ServiceClient();
	}

	return _serviceClient;
}
````
