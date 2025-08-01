.. raw:: latex

    \clearpage

.. _sec initialization:

==============
Initialization
==============

To initialize a TimeTagger4:

- Get a default set of initialization parameters using
  :c:func:`timetagger4_get_default_init_parameters`.
- Change parameters of :c:struct:`timetagger4_init_parameters` according to your
  specific requirements.
- Initialize a TimeTagger4 device using :c:func:`timetagger4_init`.
- Release all resources using :c:func:`timetagger4_close`.

The following example shows a basic setup of a TimeTagger4 using the default
initialization parameters.
A complete coding example can be found on
`github.com/cronologic-de/xtdc_babel <https://github.com/cronologic-de/xtdc_babel>`__
or in Section :ref:`sec code example`.

.. code-block:: C

    // get a default set of initialization parameters
    timetagger4_init_parameters params;
    status = timetagger4_get_default_init_parameters(&params);
    if (status != TIMETAGGER4_OK) { /* handle error */ }

    // initialize a device
    const char* err_message;
    timetagger4_device* device = timetagger4_init(&params, &status, &err_message);
    if (status != TIMETAGGER4_OK) { /* handle error */ }

    // use device

    // after usage, free up all resources by closing the device
    status = timetagger4_close(device)



timetagger4_get_default_init_parameters
=======================================

.. c:function:: int timetagger4_get_default_init_parameters(\
    timetagger4_init_parameters *init)

    Initialize a :c:struct:`timetagger4_init_parameters` struct with default values.

    You should always use this method first to set up your initialization parameters,
    then adjust the parameters to your specific needs.

    :param init: Pointer to a :c:struct:`timetagger4_init_parameters` struct that
        will be filled.

    :returns: Status codes:
        :c:macro:`TIMETAGGER4_OK` or
        :c:macro:`TIMETAGGER4_CRONO_INVALID_ARGUMENTS`.

timetagger4_init
================

.. c:function:: timetagger4_device timetagger4_init(\
    timetagger4_init_parameters *params,\
    int *error_code,\
    char **error_message)

    Opens and initializes the TimeTagger4 board with index
    :c:member:`params.card_index <timetagger4_init_parameters.card_index>`.

    :param params: Pointer to a :c:struct:`timetagger4_init_parameters`.
        The struct must have been completely initialized using
        :c:func:`timetagger4_get_default_init_parameters`.

    :param error_code: Pointer to the location where a potential error code will be
        stored.
        Equals :c:macro:`TIMETAGGER4_OK` if no error occurred. Otherwise can be
        :c:macro:`TIMETAGGER4_CRONO_INVALID_ARGUMENTS`,
        :c:macro:`TIMETAGGER4_DEVICE_OPEN_FAILED`,
        :c:macro:`TIMETAGGER4_HARDWARE_FAILURE`,
        :c:macro:`TIMETAGGER4_INVALID_BUFFER_PARAMETERS`,
        :c:macro:`TIMETAGGER4_CRONO_INTERNAL_ERROR`, or
        :c:macro:`TIMETAGGER4_WRONG_STATE`.


    :param error_message: Pointer to a location where a potential error message in plain
        text will be stored.

    :return: The TimeTagger4 device corresponding to
        :c:member:`params.card_index <timetagger4_init_parameters.card_index>`.


timetagger4_close
=================

.. c:function:: int timetagger4_close(timetagger4_device *device)

    Close an initialized TimeTagger4 device, releasing all resources.

    :param device: Pointer to the device that shall be closed.

    :returns: Status code:
        :c:macro:`TIMETAGGER4_OK`,
        :c:macro:`TIMETAGGER4_INVALID_DEVICE`,
        :c:macro:`TIMETAGGER4_WRONG_STATE`, or
        :c:macro:`TIMETAGGER4_CRONO_INTERNAL_ERROR`.


timetagger4_init_parameters
===========================

.. include:: structs/timetagger4_init_parameters.rst

timetagger4_device
==================

.. c:struct:: timetagger4_device

    Structure referencing an initialized TimeTagger4 device.

    .. c:member:: void* timetagger4
