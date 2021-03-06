---
title: Overview
meta_title: PHP server-side wrapper for the Kendo UI Calendar widget
meta_description: Getting started with Kendo UI Calendar for PHP in quick steps - configure Kendo UI Calendar widget and operate Kendo UI Calendar events.
slug: php-calendar-overview
publish: true
relatedDocs: php-ui-calendar
---

# Calendar

The Kendo Calendar for PHP is a server-side wrapper for the [Kendo UI Calendar](http://docs.kendoui.com/api/web/calendar) widget.

## Getting Started

Here is how to configure a simple Kendo Calendar:

1. Follow the steps from the [introduction](/getting-started/using-kendo-with/php/introduction) - include the autoloader, JavaScript and CSS files.

2. Create a [calendar](/api/wrappers/php/Kendo/UI/Calendar), configure its [min](/api/wrappers/php/Kendo/UI/Calendar#min),
[max](/api/wrappers/php/Kendo/UI/Calendar#max) and [value](/api/wrappers/php/Kendo/UI/Calendar#value) options.

        <?php
        $calendar = new \Kendo\UI\Calendar('calendar');
        $calendar->min(new DateTime('1900-01-01'))
                 ->max(new DateTime('2099-12-31'))
                 ->value(new DateTime('today', new DateTimeZone('UTC')));
        ?>

## Getting Client-side Reference

You can reference the client-side Kendo Calendar instance via [jQuery.data()](http://api.jquery.com/jQuery.data/).
Once a reference has been established, you can use the [API](/api/web/calendar#methods) to control its behavior.


### Example

    <?php
    $calendar = new \Kendo\UI\Calendar('calendar');
    echo $calendar->render();
    ?>
    <script>
    $(function() {
        // The constructor parameter is used as the 'id' HTML attribute of the calendar
        var calendar = $("#calendar").data("kendoCalendar")
    });
    </script>

## Handling Events

You can subscribe to all calendar [events](/api/web/calendar#events).

### Example - subscribing by specifying JavaScript function name

    <?php
    $calendar = new \Kendo\UI\Calendar('calendar');

    // The 'calendar_change' JavaScript function will handle the 'change' event of the calendar
    $calendar->change('calendar_change');

    echo $calendar->render();
    ?>
    <script>
    function calendar_change() {
        // Handle the change event
    }
    </script>

### Example - providing inline JavaScript code

    <?php
    $calendar = new \Kendo\UI\Calendar('calendar');

    // Provide inline JavaScript code that will handle the 'change' event of the calendar
    $calendar->change('function() { /* Handle the change event */ }');

    echo $calendar->render();
    ?>
