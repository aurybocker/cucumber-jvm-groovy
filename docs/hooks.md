# Hooks

Hooks are blocks of code that can run at various points in the Cucumber execution cycle.
They are typically used for setup and teardown of the environment before and after each scenario.

See the [reference documentation](https://docs.cucumber.io/docs/cucumber/api/#hooks).

## Scenario hooks

Scenario hooks run for every scenario.

### Before

`Before` hooks run before the first step of each scenario.

```groovy
Before() { scenario ->
  // Do something before each scenario
}

// Or:
Before() {
  // Do something before each scenario
}
```

### After

`After` hooks run after the last step of each scenario.

```groovy
After() { scenario ->
  // Do something after each scenario
}

// Or:
After() {
  // Do something after each scenario
}
```

## Step hooks

Step hooks invoked before and after a step.

### BeforeStep

```groovy
BeforeStep() { scenario ->
  // Do something before step
}

// Or:
BeforeStep() {
  // Do something before step
}
```

### AfterStep

```groovy
AfterStep() { scenario ->
  // Do something after step
}

// Or:
AfterStep() {
  // Do something after step
}
```

## Conditional hooks

Hooks can be conditionally selected for execution based on the tags of the scenario.

```groovy
Before("@browser and not @headless") { 
  // Do something before each scenario with tag @browser but not @headless
}
```

## Order

You can define an order between multiple hooks.

```groovy
Before(10) { 
  // Do something before each scenario
}

Before(20) { 
  // Do something before each scenario
}
```

The **default order is 1000**.

## Conditional and order

You mix up conditional and order hooks with following syntax:

```groovy
Before("@browser and not @headless", 10) {
  // Do something before each scenario
}
```
