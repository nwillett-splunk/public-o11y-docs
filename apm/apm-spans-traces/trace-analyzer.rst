.. _trace-analyzer:

****************************************
Explore your traces using Trace Analyzer
****************************************

.. meta::
   :description: Use Trace Analyzer inside Splunk APM to detect patterns across billions of transactions to identify “unknown unknowns” problems across any combinations of tags, services, and users in your environment.

Trace Analyzer lets you search traces generated by your application and identify patterns in the full-fidelity trace data without prior knowledge of which tags are relevant. 

Trace Analyzer is available to all Splunk Observability Cloud Splunk APM users. 

Examples of questions that Trace Analyzer helps you answer include:

-  How many traces and traces with errors exist for a given combination of service, environment, and tags?
-  For a given issue, which customers experience the highest error rate?
-  How to locate error spikes in my trace data?

When to use Trace Analyzer
=============================================

Splunk Observability Cloud provides several tools for exploring application monitoring data. Trace Analyzer is suited to scenarios where you have high-cardinality, high-granularity searches and explorations to research unknown or new issues. See :ref:`guideline-cardinality`.

The following table presents what each APM tool is best suited for:

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 20 20
   :width: 100

   * - APM tool
     - Scenario
     - Analysis level
     - Cardinality 
     - Documentation

   * - Trace Analyzer
     - Identify patterns for unindexed tags
     - Trace-level analysis
     - High cardinality
     - 

   * - Tag Spotlight and service map
     - Surface trends for indexed tags
     - Service-level analysis
     - Medium cardinality
     - :ref:`apm-tag-spotlight`

   * - Monitoring MetricSets
     - Get alerts on service degradation
     - Workflow and service-level analysis
     - Low cardinality
     - :ref:`cmms`

Explore your trace data
=========================

To open Trace Analyzer, select :guilabel:`Traces` in Splunk APM and select :guilabel:`Switch to Trace Analyzer`. To switch back to the classic traces view, select :guilabel:`Switch to Classic View`. See :ref:`trace-search` for more info about the classic traces view.

To explore your trace data, use the following controls, which are numbered as callouts in the image. Additional details for each callout follow the image:

..  image:: /_images/apm/trace-analyzer/TraceAnalyzerControls_sampling.png
    :width: 95%
    :alt: Elements of the Trace Analyzer user interface

#. Use the filter bar to refine the traces by time range, environment, workflow, services, and tags.
#. Use the minimum and maximum trace duration to refine the traces that are included by their duration.
#. Use the sample ratio to select all traces or 10% of traces. 
#. Use the :guilabel:`Errors Only` switch to show only traces with errors.
#. Use the search to look up a trace by its ID.
#. Use the real-time chart to view the count of total traces with errors.
#. Use the table of traces to view trace details or group metrics based on a tag. 

Trace Analyzer searches all traces within the default retention period of 8 days. See :ref:`apm-data-retention` to learn more about the default trace retention period.

Explore trace and error counts
-------------------------------

Trace Analyzer shows total traces and traces with errors in a stacked bars chart. Select and drag over the bars in the chart to select a specific period within the available time frame. Select :guilabel:`Filter to selection` to update the time range filter.

..  image:: /_images/apm/trace-analyzer/TraceDragDropChart.gif
    :width: 95%
    :alt: Selection of a specific time frame

Group by tag
-------------------------------

You can group all available traces by a single tag or attribute. For example, you can group all traces from your service by database table, host name, or HTTP status code.

..  image:: /_images/apm/trace-analyzer/TraceSelectTag.png
    :width: 95%
    :alt: Tag selection menu of Trace Analyzer

The resulting :guilabel:`Group Metrics` tab shows a breakdown of the top 100 values for the selected tag, ranked by the number of errors.


..  image:: /_images/apm/trace-analyzer/MetricTables.png
    :width: 95%
    :alt: Metric table in Trace analyzer

You can order both tables by the number of matching traces.

Trace Analyzer trace limits
==================================

Trace Analyzer can search a maximum of 6 hours of data. 

Within the Trace Analyzer interface, there are three different display limits. The Trace Analyzer chart (1) and the Group Metrics (2) tab display up to 6 hours of traces. The list of traces displayed on the Traces tab (3) has a limit of 1,000 traces. For the Traces tab, Trace Analyzer searches for traces at the end of the time window you select. When 1,000 traces are matched or the six-hour search window is reached, the list stops populating.

..  image:: /_images/apm/trace-analyzer/TraceAnalyzerLimit.png
    :width: 95%
    :alt: Trace limit in trace list

Learn more
=====================

See the following links for more information on Trace Analyzer: 

* :ref:`apm-scenario-trace-analyzer`