.. raw:: latex

    \clearpage

.. _sec configuration:

=============
Configuration
=============

After a TimeTagger4 device has been initialized (see :ref:`sec initialization`), it
must be configured before it can acquire data.

To configure a TimeTagger device:

- Get a default set of configuration parameters using
  :c:func:`timetagger4_get_default_configuration`.
- Change parameters of :c:struct:`timetagger4_configuration` according to your
  specific requirements.
- Configure the TimeTagger4 device using :c:func:`timetagger4_configure`.

The following example shows a basic configuration of an already initialized TimeTagger4
device using the default configuration parameters.
A complete coding example can be found on
`github.com/cronologic-de/xtdc_babel <https://github.com/cronologic-de/xtdc_babel>`__
or in Section :ref:`sec code example`.

.. code-block:: C

    // get a default set of configuration parameters
    timetagger4_configuration config;
    status = timetagger4_get_default_configuration(device, &config);
    if (status != TIMETAGGER4_OK) { /* handle error */ }

    // configure the device
    status = timetagger4_configure(device, &config);
    if (status != TIMETAGGER4_OK) { /* handle error */ }


timetagger4_configure
=====================

.. c:function:: int timetagger4_configure(\
    timetagger4_device *device,\
    timetagger4_configuration *config)

    Configures a TimeTagger4 device.

    :param device: Pointer to a TimeTagger4 device.
    :param config: Pointer to a :c:struct:`timetagger4_configuration` struct used
        for the configuration.
    :return: Status code: TODO


timetagger4_get_default_configuration
=====================================

.. c:function:: int timetagger4_get_default_configuration(\
    timetagger4_device *device,\
    timetagger4_configuration *config)

    Obtain a default set of configuration parameters.

    :param device: Pointer to a TimeTagger4 device.
    :param config: Pointer to a :c:struct:`timetagger4_configuration` struct that
        will be filled.
    :return: Status code: TODO


timetagger4_get_current_configuration
=====================================

.. c:function:: int timetagger4_get_current_configuration(\
    timetagger4_device *device,\
    timetagger4_configuration *config)

    Obtain the current set of configuration parameters of an already configured
    TimeTagger4 device.

    :param device: Pointer to a configured TimeTagger4 device.
    :param config: Pointer to a :c:struct:`timetagger4_configuration` struct that
        will be filled.
    :return: Status code: TODO

timetagger4_configuration
=========================

.. include:: structs/timetagger4_configuration.rst


timetagger4_trigger
===================

.. include:: structs/timetagger4_trigger.rst


timetagger4_tiger_block
=======================

.. include:: structs/timetagger4_tiger_block.rst


timetagger4_channel
===================

.. include:: structs/timetagger4_channel.rst


timetagger4_delay_config
========================

.. include:: structs/timetagger4_delay_config.rst