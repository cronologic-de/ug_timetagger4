.. raw:: latex

    \clearpage

==================
Driver Information
==================

timetagger4_get_driver_revision
===============================

.. c:function:: int timetagger4_get_driver_revision()

    Get the driver revision of the installed TimeTagger4 driver.

    This function does not require a TimeTagger4 board to be installed in the system.

    :return: The driver version in the same format as 
             :c:member:`timetagger4_static_info.driver_revision`.


timetagger4_get_driver_revision_str
===================================

.. c:function:: const char* timetagger4_get_driver_revision_str()

    Get the driver revision of the installed TimeTagger4 driver.

    This function does not require a TimeTagger4 board to be installed in the system.

    :return: The driver version including the SVN build revision as a string.


timetagger4_count_devices
=========================

.. c:function:: int timetagger4_count_devices(int *error_code, char **error_message)

    Count the number of boards installed in the system that are supported by the
    installed TimeTagger4 driver.

    :param error_code: Pointer to the location where a potential error code will be
        stored. Equals :c:macro:`TIMETAGGER4_OK` if no error occurred.
    :param error_message: Pointer to a location where a potential error message in plain
        text will be stored.
    :return: The number of boards.