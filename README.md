# Micronaut Lambda Subtypes

This example project shows how to build an AWS Lambda function with Micronaut and Kotlin. The function takes polymorphic JSON input, and Jackson subtypes decide which command class each request is turned into.

## What it is

The project has a custom Micronaut request stream handler that sends every request to one function bean. Incoming JSON goes to an abstract command type. Jackson type information picks the concrete command based on a type property. The function returns a simple response that depends on which command it received. The project was written to go with a blog post about building a Micronaut AWS Lambda API with Jackson subtypes.

## Main technologies

- Kotlin on the JVM (Java 11)
- Micronaut with the AWS Lambda runtime
- Jackson databind with the Kotlin module
- Gradle (Kotlin DSL) with the Shadow plugin to build a deployable fat jar
- JUnit 5 for tests

## Structure

- Gradle build configuration and the wrapper are in the project root
- The main source folder holds the function bean, the command and response types, and the Lambda request stream handler
- The resources folder holds the application and logging configuration
- The test source folder holds a test for the handler

## Status

This is a finished example from 2022 and is not maintained.