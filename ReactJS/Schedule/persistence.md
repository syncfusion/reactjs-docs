---
title: State persistence
description: Persisting Schedule Properties
platform: ReactJS
control: schedule
documentation: ug
keywords: persist, state persist, persistence, state persistence
---
# Persistence

State persistence allows the Scheduler to retain the current model value in the browser cookies for state maintenance. This action is handled through the property [enablePersistence](/api/js/ejschedule#members:enablepersistence) which is set to false by default.

When it is set to **true**, some of the Schedule control model values will be retained even after refreshing the page which are listed below.

<table>
    <tr>
        <td>currentView</td>
        <td>timeMode</td>
    </tr>
    <tr>
        <td>firstDayOfWeek</td>
        <td>dateFormat</td>
    </tr>
    <tr>
        <td>isDST</td>
        <td>timeZone</td>
    </tr>
    <tr>
        <td>timeScale</td>
        <td>startHour</td>
    </tr>
    <tr>
        <td>endHour</td>
        <td>workHours</td>
    </tr>
    <tr>
        <td>Height</td>
        <td>Width</td>
    </tr>
    <tr>
        <td>cellHeight</td>
        <td>cellWidth</td>
    </tr>
    <tr>
        <td>currentDate</td>
        <td>minDate</td>
    </tr>
    <tr>
        <td>maxDate</td>
        <td>renderDates</td>
    </tr>
    <tr>
        <td>orientation</td>
        <td>views</td>
    </tr>
    <tr>
        <td>workWeek</td>
        <td>agendaViewSettings.daysInAgenda</td>
    </tr>
    <tr>
        <td>enableLoadOnDemand</td>
        <td>showLocationField</td>
    </tr>
    <tr>
        <td>showAllDayRow</td>
        <td>isResponsive</td>
    </tr>
    <tr>
        <td>enableRecurrenceValidation</td>
        <td>showOverflowButton</td>
    </tr>
    <tr>
        <td>allowDragAndDrop</td>
        <td>showDeleteConfirmationDialog</td>
    </tr>
    <tr>
        <td>showNextPrevMonth</td>
        <td>appointmentDragArea</td>
    </tr>
</table>

The Schedule properties that are not retained while maintaining state persistence are included within the **ignoreOnPersist** list, which makes it not to persist by default.
