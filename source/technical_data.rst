==============
Technical Data
==============

Each board is tested against the values listed in the columns “Min” and “Max”.
“Typical” (Typ.) is the mean value of the first 10 boards produced or a value that is
set by design.

Dimension
=========

The TimeTagger4 boards fit any standard full-height PCIe slot and occupy a single
slot width.

The dimensions, excluding the slot bracket,
are **167.7 × 111.15 × 16.8 mm** (depths × height × width).

TDC Characteristics
===================


TDC Measurement Characteristics for Gen 1
-----------------------------------------

.. tabularcolumns:: p{1.8cm}|p{9.4cm}|p{0.9cm}|p{0.9cm}|p{0.9cm}|p{1.1cm}

.. table::
    :width: 100%

    +--------------------+-----------------------------------------+-----+---------+-------+---------+
    | Symbol             | Parameter                               | Min | Typ.    | Max   | Units   |
    +====================+=========================================+=====+=========+=======+=========+
    | INL                | Integral non-linearity                  |     |         | 0.5   | bins    |
    +--------------------+-----------------------------------------+-----+---------+-------+---------+
    | DNL                | Differential non-linearity              |     | 0.2     |       | bins    |
    +--------------------+-----------------------------------------+-----+---------+-------+---------+
    | t\ :sub:`Data`     | Data format bin size                    |     | 500     |       | ps      |
    +--------------------+-----------------------------------------+-----+---------+-------+---------+
    | t\ :sub:`Res1`     | Double pulse resolution for -1G         |     | 1000    |       | ps      |
    +--------------------+-----------------------------------------+-----+---------+-------+---------+
    | t\ :sub:`Res2`     | Double pulse resolution for -2G         |     | 500     |       | ps      |
    +--------------------+-----------------------------------------+-----+---------+-------+---------+
    | Δt\ :sub:`Start`   | Interval between consecutive starts     | 4   |         |       | ns      |
    +--------------------+-----------------------------------------+-----+---------+-------+---------+
    | t\ :sub:`Range`    | Measurement range using hits only       |     | 8.368   |       | ms      |
    +--------------------+-----------------------------------------+-----+---------+-------+---------+
    | t\ :sub:`Extended` | Extended range using rollovers          |     | 2.147   |       | s       |
    +--------------------+-----------------------------------------+-----+---------+-------+---------+
    | f\ :sub:`Readout`  | Readout rate                            |     |         | 48    | MHits/s |
    +--------------------+-----------------------------------------+-----+---------+-------+---------+

.. _sec tdc specs:

TDC Measurement Characteristics for Gen 2
-----------------------------------------

.. tabularcolumns:: p{1.8cm}|p{9.4cm}|p{0.9cm}|p{0.9cm}|p{0.9cm}|p{1.1cm}

.. table::
    :width: 100%

    +--------------------------+------------------------------------------+-----+---------+---------+------------------+
    | Symbol                   | Parameter                                | Min | Typ.    | Max     | Units            |
    +==========================+==========================================+=====+=========+=========+==================+
    | INL                      | Integral non-linearity                   |     |         | 0.5     | bins             |
    +--------------------------+------------------------------------------+-----+---------+---------+------------------+
    |                          | Differential non-linearity               |     |         |         |                  |
    |                          +------------------------------------------+-----+---------+---------+                  |
    | DNL                      | -1.25G to -5G                            |     |         | 0.01    | t\ :sub:`Data`   |
    |                          +------------------------------------------+-----+---------+---------+                  |
    |                          | -10G                                     |     |         | 0.3     |                  |
    +--------------------------+------------------------------------------+-----+---------+---------+------------------+
    | t\ :sub:`Data`           | Data format bin size                     |     | 100     |         | ps               |
    +--------------------------+------------------------------------------+-----+---------+---------+------------------+
    |                          |   Quantization                           |     |         |         | ps               |
    |                          +------------------------------------------+-----+---------+---------+                  |
    |                          |    -1.25G                                |     |   800   |         |                  |
    |                          +------------------------------------------+-----+---------+---------+                  |
    | t\ :sub:`Quant`          |    -2.5G                                 |     |   400   |         |                  |
    |                          +------------------------------------------+-----+---------+---------+                  |
    |                          |    -5G                                   |     |   200   |         |                  |
    |                          +------------------------------------------+-----+---------+---------+                  |
    |                          |    -10G                                  |     |   100   |         |                  |
    +--------------------------+------------------------------------------+-----+---------+---------+------------------+
    | t\ :sub:`Res`            | Double pulse resolution                  |     | 2       |         | t\ :sub:`Quant`  |
    +--------------------------+------------------------------------------+-----+---------+---------+------------------+
    | t\ :sub:`Range`          | Measurement range using hits only        |     |         | 1.677   | ms               |
    +--------------------------+------------------------------------------+-----+---------+---------+------------------+
    | t\ :sub:`Extended`       | Extended range using rollovers           |     |         | 0.429   | s                |
    +--------------------------+------------------------------------------+-----+---------+---------+------------------+
    |                          |   Burst rate for up to 4096 starts       |     |         |         | GHz              |
    |                          +------------------------------------------+-----+---------+---------+                  |
    |                          |    -1.25G                                |     |         |   0.625 |                  |
    |                          +------------------------------------------+-----+---------+---------+                  |
    | f\ :sub:`Start,burst`    |    -2.5G                                 |     |         |   1.25  |                  |
    |                          +------------------------------------------+-----+---------+---------+                  |
    |                          |    -5G                                   |     |         |   2.5   |                  |
    |                          +------------------------------------------+-----+---------+---------+                  |
    |                          |    -10G                                  |     |         |   5     |                  |
    +--------------------------+------------------------------------------+-----+---------+---------+------------------+
    | f\ :sub:`Start,sust`     | Sustained rate of starts                 |     |         | 18      | MHz              |
    +--------------------------+------------------------------------------+-----+---------+---------+------------------+
    |                          |   Burst rate for up to 3900 stops        |     |         |         | GHits/s          |
    |                          +------------------------------------------+-----+---------+---------+                  |
    |                          |    -1.25G                                |     |         |   0.625 |                  |
    |                          +------------------------------------------+-----+---------+---------+                  |
    | f\ :sub:`Stop,burst`     |    -2.5G                                 |     |         |   1.25  |                  |
    |                          +------------------------------------------+-----+---------+---------+                  |
    |                          |    -5G                                   |     |         |   2.5   |                  |
    |                          +------------------------------------------+-----+---------+---------+                  |
    |                          |    -10G                                  |     |         |   5     |                  |
    +--------------------------+------------------------------------------+-----+---------+---------+------------------+
    | f\ :sub:`Readout,single` | Readout rate per channel                 |     |         | 40      | MHits/s          |
    +--------------------------+------------------------------------------+-----+---------+---------+------------------+
    | f\ :sub:`Readout,all`    | Readout rate of all channels             |     |         | 60      | MHits/s          |
    +--------------------------+------------------------------------------+-----+---------+---------+------------------+


Oscillator Time Base
--------------------

.. tabularcolumns:: p{1.8cm}|p{9.4cm}|p{0.9cm}|p{0.9cm}|p{0.9cm}|p{1.1cm}

.. table::
    :width: 100%

    +----------------+------------------------------------------+-----+---------+-----+-------+
    | Symbol         | Parameter                                | Min | Typ.    | Max | Units |
    +================+==========================================+=====+=========+=====+=======+
    | ΔT             | Temperature stability 20°C to 70°C       |     |         | 250 | ppb   |
    +----------------+------------------------------------------+-----+---------+-----+-------+
    | F              | Initial calibration                      |     |         | 1   | ppm   |
    +----------------+------------------------------------------+-----+---------+-----+-------+
    | ΔF/F\ :sub:`1` | Aging first year                         |     |         | 2   | ppm   |
    +----------------+------------------------------------------+-----+---------+-----+-------+
    | ΔF/F\ :sub:`10`| Aging 10 years                           |     |         | 8   | ppm   |
    +----------------+------------------------------------------+-----+---------+-----+-------+


Electrical Characteristics
==========================

Power Supply
------------

.. tabularcolumns:: p{1.8cm}|p{9.4cm}|p{0.9cm}|p{0.9cm}|p{0.9cm}|p{1.1cm}

.. table::
    :width: 100%

    +-----------------+----------------------------------------------------+------+---------+------+-------+
    | Symbol          | Parameter                                          | Min  | Typ.    | Max  | Units |
    +=================+====================================================+======+=========+======+=======+
    | P\ :sub:`total` | Total power consumption                            |      |         | 10   | W     |
    +-----------------+----------------------------------------------------+------+---------+------+-------+
    | VCC\ :sub:`3.3` | PCIe 3.3 V rail power supply voltage               | 3.1  | 3.3     | 3.5  | V     |
    +-----------------+----------------------------------------------------+------+---------+------+-------+
    | I\ :sub:`3.3`   | PCIe 3.3 V rail input current                      |      |         | 650  | mA    |
    +-----------------+----------------------------------------------------+------+---------+------+-------+
    | VCC\ :sub:`12`  | PCIe 12 V rail power supply voltage                | 11.1 | 12.0    | 12.9 | V     |
    +-----------------+----------------------------------------------------+------+---------+------+-------+
    | I\ :sub:`12`    | PCIe 12 V rail input current                       |      |         | 550  | mA    |
    +-----------------+----------------------------------------------------+------+---------+------+-------+
    | VCC\ :sub:`aux` | PCIe 3.3 V\ :sub:`Aux` rail power supply voltage   |      | 3.3     |      | V     |
    +-----------------+----------------------------------------------------+------+---------+------+-------+
    | I\ :sub:`aux`   | PCIe 3.3 V\ :sub:`Aux` rail input current          |      | 0       |      | mA    |
    +-----------------+----------------------------------------------------+------+---------+------+-------+

.. _sec tdc inputs:

TDC Inputs
----------

The TimeTagger4’s inputs are single-ended AC-coupled with 50 Ω termination.

All inputs are AC-coupled. The inputs have very high input bandwidth requirements and
therefore there are no circuits that provide over-voltage protection for these signals.

Keep in mind, that the input baseline V\ :sub:`Base` is affected by the ratio of
pulse length t\ :sub:`Pulse` to average pulse distance (for continuous signals the
term is called duty cycle).

.. attention:: 

    Any voltage on the inputs above **5 V or below −5 V** relative to the voltage of
    the slot cover can result in permanent damage to the board.

.. attention::

    Make sure not to drive the inputs when the connector is configured as a
    :ref:`TiGer <sec tiger>` output.

.. tabularcolumns:: p{1.8cm}|p{7.0cm}|p{2.1cm}|p{0.9cm}|p{2.1cm}|p{1.1cm}

.. table::
    :width: 100%

    +--------------------+-------------------------------------+-----------------------+---------+-----------------------+-------+
    | Symbol             | Parameter                           | Min                   | Typ.    | Max                   | Units |
    +====================+=====================================+=======================+=========+=======================+=======+
    | V\ :sub:`Base`     | Input Baseline\ :sup:`1`            | –5                    |         | 5                     | V     |
    +--------------------+-------------------------------------+-----------------------+---------+-----------------------+-------+
    | V\ :sub:`Threshold`| Trigger Level                       | V\ :sub:`Base` – 1.27 |         | V\ :sub:`Base` + 1.13 | V     |
    +--------------------+-------------------------------------+-----------------------+---------+-----------------------+-------+
    | \|ΔV\ :sub:`min`\| | Magnitude of minimal pulse height   | 10                    |         |                       | mV    |
    +--------------------+-------------------------------------+-----------------------+---------+-----------------------+-------+
    |                    |   Pulse Length                      |                       |         |                       |       |
    |                    +-------------------------------------+-----------------------+---------+-----------------------+       |
    |                    |    -1.25G                           |   0.8                 |         |                       |       |
    |                    +-------------------------------------+-----------------------+---------+-----------------------+       |
    | t\ :sub:`Pulse`    |    -2.5G                            |   0.4                 | 5       | 200                   | ns    |
    |                    +-------------------------------------+-----------------------+---------+-----------------------+       |
    |                    |    -5G                              |   0.2                 |         |                       |       |
    |                    +-------------------------------------+-----------------------+---------+-----------------------+       |
    |                    |    -10G                             |   0.1                 |         |                       |       |
    +--------------------+-------------------------------------+-----------------------+---------+-----------------------+-------+
    | t\ :sub:`Rise`     | Pulse Edge 20% to 80%               |                       |         | 10                    | ns    |
    +--------------------+-------------------------------------+-----------------------+---------+-----------------------+-------+
    | t\ :sub:`Fall`     | Pulse Edge 80% to 20%               |                       |         | 10                    | ns    |
    +--------------------+-------------------------------------+-----------------------+---------+-----------------------+-------+
    | Z\ :sub:`p`        | Input Impedance                     |                       | 50      |                       | Ω     |
    +--------------------+-------------------------------------+-----------------------+---------+-----------------------+-------+
    | I\ :sub:`Term`     | Termination Current                 | –50                   | –20     | 50                    | mA    |
    +--------------------+-------------------------------------+-----------------------+---------+-----------------------+-------+

:sup:`1` Be wary that the total input voltage (baseline + pulse) does not exceed ±5 V!


Information Required by DIN EN 61010-1
======================================

.. _sec manufacturer:

Manufacturer
------------

The TimeTagger4 is a product of:

| cronologic GmbH & Co. KG
| Jahnstraße 49
| D-60318 Frankfurt
|
| Germany HRA 42869 beim Amtsgericht Frankfurt/M
| VAT-ID: DE235184378
| PCI Vendor ID: 0x1A13


Intended Use and System Integration
-----------------------------------

The devices are not ready to use as delivered by cronologic. It requires the
development of specialized software to fulfill the application of the end-user.
The device is provided to system integrators to be built into measurement
systems that are distributed to end users. These systems usually consist of the
TimeTagger4, a main board, a case, application software and possibly additional
electronics to attach the system to some type of detector. They might also be
integrated with the detector.

The TimeTagger4 is designed to comply with DIN EN 61326-1 when operated on a
PCIe compliant main board housed in a properly shielded enclosure. When
operated in a closed standard compliant enclosure the device does not pose any
hazards as defined by DIN EN 61010-1.

Radiated emissions, noise immunity, and safety highly depend on the quality of
the enclosure. It is the responsibility of the system integrator to ensure that
the assembled system is compliant to applicable standards of the country that
the system is operated in, especially regarding user safety and electromagnetic
interference.

When handling the board, adequate measures must be taken to protect the
circuits against electrostatic discharge (ESD). All power supplied to the
system must be turned off before installing the board.


Environmental Conditions for Storage
------------------------------------

The board shall be stored between operation under the following conditions:

.. table::
    :width: 100%

    +------------------+------------------------------------------+-------+---------+-----+-------+
    | Symbol           | Parameter                                | Min   | Typ.    | Max | Units |
    +==================+==========================================+=======+=========+=====+=======+
    | T\ :sub:`store`  | ambient temperature                      | –30   |         | 60  | °C    |
    +------------------+------------------------------------------+-------+---------+-----+-------+
    | RH\ :sub:`store` | relative humidity at 31°C noncondensing  | 10    |         | 70  | %     |
    +------------------+------------------------------------------+-------+---------+-----+-------+

Environmental Conditions for Operation
--------------------------------------

.. table::
    :width: 100%

    +------------------+-----------------------------+-----+---------+-----+-------+
    | Symbol           | Parameter                   | Min | Typ.    | Max | Units |
    +==================+=============================+=====+=========+=====+=======+
    | T\ :sub:`oper`   | ambient temperature         | 5   |         | 40  | °C    |
    +------------------+-----------------------------+-----+---------+-----+-------+
    | RH\ :sub:`oper`  | relative humidity at 31°C   | 20  |         | 75  | %     |
    +------------------+-----------------------------+-----+---------+-----+-------+

.. attention::

    Do not connect any DC-coupled inputs to a channel while the
    :ref:`TiGer <sec tiger>` of that channel is configured as an output. Doing so
    could permanently damage the TimeTagger4 and the external hardware.


Cooling
-------

The TimeTagger4 in its base configuration has passive cooling that requires a
certain amount of airflow. If the case design can’t provide enough airflow to
the board, a slot cooler like Zalman ZM-SC100 can be placed next to the board.
Active cooling is also available as an option for the board.


Recycling
---------

cronologic is registered with the “Stiftung Elektro-Altgeräte Register” as a
manufacturer of electronic systems with Registration ID DE 77895909.  The
TimeTagger4 belongs to category 6, “Kleine Geräte der Informations- und
Telekommunikationstechnik für die ausschließliche Nutzung in anderen als
privaten Haushalten.” Devices sold before 2018 belong to category 9,
“Überwachungs und Kontrollinstrumente für ausschließlich gewerbliche Nutzung.”
The last owner of a TimeTagger4 must recycle it, treat the board in compliance
with §11 and §12 of the German ElektroG, or return it to the manufacturer’s
address listed under :ref:`sec manufacturer`.