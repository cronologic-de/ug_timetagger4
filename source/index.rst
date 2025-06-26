TimeTagger4 User Guide
======================


.. raw:: latex

    \RaggedRight

.. raw:: latex 

    \phantomsection
    \addcontentsline{toc}{chapter}{Introduction}
    \chapter*{Introduction}


The TimeTagger4 is a *common-start* low resolution, high throughput time-to-digital
converter. Timestamps of leading or trailing edges (or both) of digital pulses are
recorded.

The TimeTagger4 produces a stream of output *packets*, each containing data from
a single start event.

The relative timestamps of all stop pulses that occur within a configurable time range
are grouped into one packet, while all pulses outside that range are discarded.

.. only:: latex

    This User Guide is also available online at 
    `docs.cronologic.de/timetagger4 <https://docs.cronologic.de/timetagger4>`_.

.. only:: html

    Features
    --------

.. raw:: latex 

    \phantomsection
    \addcontentsline{toc}{section}{Features}
    \section*{Features}


- **4-channel common-start TDC**
- **Quantization** (measurement resolution): **100 to 1000 ps**
- **Standard range**: 8.388 ms for Gen 1 and **1.677 ms** for **Gen 2** (24 bits)
- **Extended range**: 2.147 s for Gen 1 and **0.428 s** for **Gen 2** (31 bits)
- **Double-pulse resolution**: twice the quantization size
- **Dead time** between groups: **none**
- **Minimum interval** between starts: 4 ns for Gen 1 and **3.2 ns** for **Gen 2**
- Up to **8000 Hits per packet**
- **5 to 0.625 GHz/s** for bursts of up to 4096 starts
- **5 to 0.625 GHits/s/channel** for bursts of up to 3900 stops
- **40 MHits/s/channel** of sustained stops
- **60 MHits/s** over all channels of sustained stops
- **PCIe x1** interface
- **Continuous mode**, supporting unlimited recording of stops without starts


.. only:: html

    TimeTagger4 Variants
    --------------------

.. raw:: latex

    \clearpage
    \phantomsection
    \addcontentsline{toc}{section}{TimeTagger4 Variants}
    \section*{TimeTagger4 Variants}

The TimeTagger4 exists in multiple variants. Each variant exists as a
PCIe board or as a standalone desktop solution. For more information see
:ref:`sec ordering information`.


.. table:: TimeTagger4 variants.
    :name: table variants
    :align: center
    :width: 100%

    +------------------------+-------------+-------------+----------+----------+----------+----------+
    | Version                | -1G         | -2G         | -1.25G   | -2.5G    | -5G      | -10G     |
    +========================+=============+=============+==========+==========+==========+==========+
    | Quantization           | 1000 ps     | 500 ps      | 800 ps   | 400 ps   | 200 ps   | 100 ps   |
    +------------------------+-------------+-------------+----------+----------+----------+----------+
    | Data Format Bin Size   | 500 ps      | 500 ps      | 100 ps   | 100 ps   | 100 ps   | 100 ps   |
    +------------------------+-------------+-------------+----------+----------+----------+----------+
    | DNL and INL            | 0.01 LSB    | 0.01 LSB    | 0.01 LSB | 0.01 LSB | 0.01 LSB | 0.3 LSB  |
    +------------------------+-------------+-------------+----------+----------+----------+----------+
    | PCIe line rate         | Gen 1       | Gen 1       | Gen 2    | Gen 2    | Gen 2    | Gen 2    |
    +------------------------+-------------+-------------+----------+----------+----------+----------+
    | Readout Rate           | 200 MB/s    | 200 MB/s    | 400 MB/s | 400 MB/s | 400 MB/s | 400 MB/s |
    +------------------------+-------------+-------------+----------+----------+----------+----------+
    | Status                 | end of life | end of life | active   | active   | active   | active   |
    +------------------------+-------------+-------------+----------+----------+----------+----------+

.. only:: html

    Applications
    ------------

.. raw:: latex

    \phantomsection
    \addcontentsline{toc}{section}{Applications}
    \section*{Applications}


The TimeTagger4 can be used in all time measuremnt applications where a common-start
setup with 100 ps resolution is sufficient.

For alternatives with higher resolution, more channels, or higher readout rates
check our TDC website at `www.cronologic.de <https://www.cronologic.de>`__.

The TimeTagger4 is well-suited for the following applications:

- LIDAR down to 8 cm resolution
- Blade oscillation measurements
- Reciprocal counters
- Coincidence measurements
- Quantum key distribution (QKD)
- Time-correlated single-photon counting (TCSPC)

.. only:: html

    Contents
    --------

.. toctree::
   :maxdepth: 2
   
   hardware
   functionality
   api_reference/index
   example
   ordering_information
   technical_data
   revhistory
   erratum
