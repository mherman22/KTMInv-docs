# KTMInv RestApi Docs

Welcome to the `KTMInv Rest Api documentation`! KTMInv is an application which enables the design of a Knitting Company REcord keeping management system.

The system is based on a conceptual database structure that includes basically three(3) data tables i.e `customer` which is used to capture details about the customer, `products` which is used to capture details about the products that are in the inventory and `payment` which is used to capture details about payments in the company.

This document provides High level documentation of OpenMRS APIs with code samples which are in the dark area to the right. If you find anything missing or incorrect please consider proposing revision on GitHub.

The Rest Api can be found at [KTMInv](https://github.com/mherman22/KTMInv).

This documentation has been created using [Slate](https://github.com/slatedocs/slate).

## Purpose

- The purpose of this documentation is to provide a brief and good taste and experience of the APIs that are used in OpenMRS community to the new developers so that they can onboard in the projects within the organization easily.

- The documentation also aims to assist the existing developers in getting to know the APIs' conceptual context and how they help the consumers during the interaction in the real world.

# Getting Started

To be able to provide your contribution to the KTMInv rest api, please do the following;-

- fork the [repository](https://github.com/mherman22/KTMInv.git>).
- clone it onto your machine by running git clone <https://github.com/mherman22/KTMInv.git>.
- make your changes and test them to ensure everything perfect.
- create a branch `git checkout -b branch-name`.
- commit your changes to your branch using `git add .` and `git commit -m "commit message"`.
- pull from origin to ensure your local repo is in sync with upstream. use `git pull origin branch-name`
- push your changes using `sgit push origin branch-name`.
- create a pull request and give it a proper description stating clearly the changes you have added.

## Schema

- All data is sent and received as JSON.

## Test endpoints

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/3ae8d7d63faf8975acb4)

## Getting Started with examples

### 1. Instructions for all the examples

> Java Code Stubs

```stubs


import okhttp3.MediaType;
import okhttp3.OkHttpClient;
import okhttp3.Request;
import okhttp3.RequestBody;
import okhttp3.Response;
import java.io.IOException;

public class Main {
    public static void main(String[] args) {
        try {
      
         // the examples go here
  
        } catch (IOException exception) {

            // handle exception here
        }
    }
}

```

### 2. Getting Started with Java Code samples

- Before executing the Java examples, get the okttp dependency jar and import it the project.

- These code stubs will be elided from all the java examples for clarity.
