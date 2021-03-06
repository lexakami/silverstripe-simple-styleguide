# Simple Styleguide Module

[![Build Status](https://travis-ci.org/benmanu/silverstripe-simple-styleguide.svg?branch=master)](https://travis-ci.org/benmanu/silverstripe-simple-styleguide)

## Overview

The module adds a new controller endpoint which can be viewed at the `/_styleguide` route, if logged in with 
admin permissions, or viewing from a dev environment. Also provides a kitchen sink template that can be used 
or overriden by your site theme to display frontend and typography components.

The `SimpleStyleguideController` class also includes a basic form (`SimpleStyleguideController::TestForm()`), and HTMLText output (`SimpleStyleguideController::getContent()`), for testing framework output.

## Installation

Run on the command line:

	$ composer require benmanu/silverstripe-simple-styleguide

or include `"benmanu/silverstripe-simple-styleguide": "~1.0"` in your project `composer.json` and run:

	$ composer update

## Usage

The styleguide template can be overriden by including a `SimpleStyleguideController.ss` file in your themes 
`template/Layout/` directory.

The `SimpleStyleguideController` class can be overriden using SilverStripes [extensions](https://docs.silverstripe.org/en/3.1/developer_guides/extending/extensions/) to either add new output functions, or modify the provided functions, by using the `updateStyleguideData` extension hook.

### Styleguide Data

An extension hook is available to override/edit the rendered template data through `updateStyleguideData`.

### Color Swatches

A simple color swatch template is available and can be overriden through the `color_swatches` config value.

```yml
SimpleStyleguideController:
  color_swatches:
    - Name: "Black"
      Description: "This color is rather dark"
      CSSColor: "#000000"
      TextColor: "#ffffff"
    - Name: "Grey"
      Description: "This color is grey"
      CSSColor: "#666666"
      TextColor: "#000000"
```
