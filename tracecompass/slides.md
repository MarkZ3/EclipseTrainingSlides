% title: Eclipse Trace Compass
% title_class:                  #empty, largeblend[123] or fullblend
% author: Bernd Hufmann
% author: Marc-André Laperle
% thankyou: Thank you
% thankyou_details:

---
title: Module 1
subtitle: Overview and Background

---
title: Trace Compass Overview

- **Framework** to build trace visualization and analysis tools

- **Scalable**: handle traces exceeding memory

- **Extensible** for any trace or log format. Binary, text, XML etc.

- **Reusable** views and widgets

- Available as standalone application or set of plug-ins


<center><img src="images/tracecompass.png"/></center>

---
title: Trace Compass Overview

- **Open source** Eclipse Project

- **EPL**

- Mostly written in **Java**

<center>
<div style="display:table-cell; width:70%;text-align: left;">
<ul>
<li>Quite active, growing community:
<ul>
	<li>Academia: École Polytechnique Montréal, Concordia, others</li>
	<li>Industry: Ericsson, EfficiOS, others</li>
	<li>Government: NSERC, DRDC, NOAA (US)</li>
	<li>Kalray</li>
	<li>Windriver</li>
</ul>
</li>
</ul>
</div>
<div style="display:table-cell; width:30%; text-align: center; vertical-align: middle"><img style="width:300px; height:auto" src="images/tracecompass_contributors.png"/></div>
<br/>
</center>

---
title: Trace Compass Overview

<center><img src="images/tracecompass_overview.png"/></center>

---
title: Trace Compass Overview
subtitle: Common Features

- Management of traces, trace formats and experiments

<center><img src="images/tracecompass_trace_management.png"/></center>

---
title: Trace Compass Overview
subtitle: Common Features

- Package export and import

<center><img src="images/tracecompass_trace_package.png"/></center>

---
title: Trace Compass Overview

- What is a trace in Trace Compass?
	- A Series of **events** over time
	- Each event has content **fields** (payload)

<center><img src="images/trace_events.png"/></center>

---
title: Trace Compass Overview
subtitle: Common Features

- Events Table
	- Implemented as an Eclipse "editor"

<center><img src="images/tracecompass_events_editor.png"/></center>

---
title: Trace Compass Overview
subtitle: Common Features

<center>
<div style="display:table-cell; width:50%;"><img style="width:300px; height:auto" src="images/tracecompass_searching.png"/></div>
<div style="display:table-cell; width:50%; text-align: center; vertical-align: middle"><span>Searching</span></div>
<br/>
<div style="display:table-cell; width:50%;"><img style="width:300px; height:auto" src="images/tracecompass_filtering.png"/></div>
<div style="display:table-cell; width:50%; text-align: center; vertical-align: middle"><span>Filtering</span></div>
<br/>
<div style="display:table-cell; width:50%;"><img style="width:300px; height:auto" src="images/tracecompass_highlighting.png"/></div>
<div style="display:table-cell; width:50%; text-align: center; vertical-align: middle"><span>Highlighting</span></div>
</center>

---
title: Trace Compass Overview
subtitle: Common Features

- Bookmarks

<center><img src="images/tracecompass_bookmarks.png"/></center>

---
title: Trace Compass Overview
subtitle: Common Features

- Sequence Diagrams
	- Translates events to sequence diagram transaction
	- Extensions can define their own model

<center><img src="images/tracecompass_sequencediagrams.png"/></center>

---
title: Trace Compass Overview
subtitle: State System

<center><img src="images/tracecompass_statesystem.png"/></center>

- State system abstracts events, analyses traces and creates models to be displayed

<center><img src="images/tracecompass_statesystem_events.png"/></center>

---
title: Trace Compass Overview
subtitle: Control Flow View

- Displays processes state changes (color-coded) over time
	- USERMODE, SYSCALL, INTERRUPED, WAIT_FOR_CPU, etc

<center><img src="images/tracecompass_controlflowview.png"/></center>

---
title: Trace Compass Overview
subtitle: Resources View

- Displays system resource states (color-coded) over time

<center><img src="images/tracecompass_resourcesview.png"/></center>

---
title: Trace Compass Overview
subtitle: CPU Usage View

- Displays % of CPU used per thread over time

<center><img src="images/tracecompass_cpuusageview.png"/></center>

---
title: Trace Compass Overview
subtitle: Call Stack View

- Shows the stack trace at any point during execution

<center><img src="images/tracecompass_callstackview.png"/></center>

---
title: Trace Compass Overview
subtitle: Critical Path

<center><img src="images/tracecompass_criticalpathview.png"/></center>

---
title: Trace Compass Overview
subtitle: Timing Analysis

<center><img style="width:700px;" src="images/tracecompass_latencyviews.png"/></center>

---
title: Trace Compass Overview
subtitle: Custom Text and XML Parsers

<center>
<div style="display:table-cell; width:50%;"><img style="width:400px;" src="images/tracecompass_customtext.png"/></div>
<div style="display:table-cell; width:50%; text-align: left; vertical-align: middle">

- Line based parser with regex defined in a wizard

- XML based extracting data from XML elements and their attributes

</div>
</center>

---
title: Trace Compass Overview
subtitle: Trace corellation (Experiments)

- Trace Compass can open **multiple traces** together to view it **as one**
	- This is called an **Experiment**
- Useful for
	- Traces coming from multiple nodes
	- Different languages
	- Different layers (network, etc)
- Traces can be manually synchronized by time or use an automatic algorithm (extensible)

---
title: Trace Compass Overview
subtitle: Integrations

- LTTng (UST, Kernel)
- Text Logs (custom parsers)
- Common Trace Format (Application, kernel, HW, Bare metal)
- Packet Capture
- BTF (Best Trace Format)
- GDB Trace Points

---
title: Common Trace Format (CTF)

- CTF is one of the trace format understood by Trace Compass
- A **metadata** file describes the trace structure, event fields, environment, etc.
	- CTF does not describe that structure, only the language to express it.
- **Channel** files contain binary data, separate from the **metadata**. There is where the events are stored.
- **LTTng** is a well known tracer that gernerates CTF traces for **Kernel** and **User Space (UST)** domains.
- Trace Compass **reads** CTF traces directly using a Java-based parser.
- Trace Compass **does not** produce CTF traces, tracers like LTTng do.
---
title: Trace Compass Overview
subtitle: References

- Project pages
	- <a href="http://tracecompass.org">tracecompass.org</a>
	- <a href="https://dev.eclipse.org/mailman/listinfo/tracecompass-dev">tracecompass-dev mailing List</a>
	- <a href="http://istmffastyet.dorsal.polymtl.ca">Is Trace Compass Fast Yet?</a>
	- <a href="http://lttng.org/">LTTng</a>
	- <a href="http://www.diamon.org/">Diamon Working Group</a>
	- <a href="http://tracingsummit.org/">Tracing Summit</a>

- Documentation
	- <a href="http://archive.eclipse.org/tracecompass/doc/org.eclipse.tracecompass.doc.user/User-Guide.html">Trace Compass User Guide</a>
	- <a href="http://archive.eclipse.org/tracecompass/doc/org.eclipse.tracecompass.doc.dev/Developer-Guide.html">Trace Compass Developer Guide</a>

---
title: The example

TODO: Explain the example application and trace here?

---
title: Module 2
subtitle: Core Trace API

---
title: Signals

- Classes can register themselves to receive various Trace-related signals
- Uses Java annotation, `@TmfSignalHandler`, to mark method that recieves the signal
- Some signals: `TmfTraceOpenedSignal`, `TmfTraceClosedSignal`, `TmfTraceRangeUpdatedSignal`

~~~java
public void foo() {
    TmfSignalManager.register(this);
}

@TmfSignalHandler
public void traceClosed(TmfTraceClosedSignal signal) {
    ...
}
~~~

---
title: Exercise: Listen to a signal

- Reset to **TRACECOMPASS1_START**
- Create a class that will receive the signal, `EventReader`
- Instantiate the class. For now, we will do this in the `Activator` class.
- Register the class with the `TmfTraceSignalManager`
- Create a `public` method that will receive the signal:
	- Annotate your method with `@TmfSignalHandler`
	- It needs a `TmfTraceOpenedSignal` parameter
	- Make it output something to the console
- <b>Go!</b>
- **TODO**: Show how to test by opening a trace

---
title: Trace API

`ITmfTrace`

- One per trace, a the central object in Trace Compass
- Knows about the key trace attributes: Number of events, file, trace type, etc.
- Allows you to seek at a location in a trace and get events one by one
- Does validation to determine whether or not a file is of this trace type (for
automatic detection, etc)

<center><image src="images/tracecompass_tmftrace_class.png"/></center>

---

title: Event Provider

- Event providers have the capability of handling event requests.
- Often implemented in pair with `ITmfTrace` in each trace type
- Of note, `getNext()` provides the next event in the trace

<center><image src="images/tracecompass_tmfeventprodider_class.png"/></center>

---
title: Event Requests

`TmfEventRequest`

- Used to obtain series of events from an event provider (usually `ITmfTrace`)
- **Asynchronous**: Send the request and receive events one by one when they are done being parsed

~~~java
eventProvider.sendRequest(new TmfEventRequest(TmfEvent.class,
        0, ITmfEventRequest.ALL_DATA,
        ITmfEventRequest.ExecutionType.BACKGROUND) {

    @Override
    public void handleData(ITmfEvent event) {
        super.handleData(event);
    }
});
~~~

---
title: Events

`ITmfEvent`

- Reprensents a single event in the trace
- Contains a **name** (event type). Use `getName()` to retrieve it.
- Contains a **time stamp**. Use `getTimestamp()` to retrieve it.
- Contains **content** (fields). Use `getContent()` to retrieve it in the form of an `ITmfEventField`. Fields can then be retrived with `getField("myfield")` for example. Fields can also have sub-fields

~~~java
ITmfEventField field = event.getContent().getField("myfield");
if (field != null) {
    System.out.println(field.getFormattedValue());
}
~~~

---
title: Exercise: Read events from the trace

- Reset to **TRACECOMPASS2_START**
- In the signal handler, get the trace object from the signal parameter
- Send an even request to the trace:
	- Create an anonymous class of type `TmfEventRequest`
	- Override handleData and output the time stamp of each event to console
		- **Bonus**: Print a specific field of the event
	- When the request is **completed**, output something to the console
- <b>Go!</b>

---
title: Module 2 Review

- **Signals** can be used to react to different things.
- **ITmfTrace** is a central object that validates if files are of this trace type, provides trace attributes, seeks to locations and retrieves events.
- **Event Requests** are a mean to obtain a series of event asynchronously.
- **Events** have a name, a time stamp and content (fields). Fields can have sub-fields.
- In the exercices:
	- We have used **signals**
	- We have retrieved **events** using **event requests** sent to the **trace** (`ITmfTrace`)

---
title: Module 7
subtitle: Timing Analysis

---
title: Timing Analysis
subtitle: Concept

- We have two metrics to analyse, what is the data and **when** did it come.
- Every event has **time** info (time stamp), let's take advantage of that.
- Measure time between a **start** and **end** state
	- Simple: Start and end **event**
	- Often: State Machine to determine start and end
	- **Start** and **End** time : <span style="border-style:solid; border-width: 5px;">**Segment**</span>


- Represent Execution times, latencies, latency chains etc.

---
title: Timing Analysis
subtitle: Why?

- Locate timing problems
- Analyse timing problems
- Find root cause and solution
- Potential delays (find problem before it occurs)
- Difficult to debug if it happens sporadically

---
title: Timing Analysis
subtitle: Example

- System Call Latency, e.g. futex

<center><img src="images/timing_systemcalls.png"/></center>

---
title: Timing Analysis
subtitle: Example

- IRQ Latency

<center><img src="images/timing_irq.png"/></center>

---
title: Timing Analysis
subtitle: Example

- High Resolution Timer – cyclictest application of rt-tests
- Latency between timer expiry till task starts

<center><img src="images/timing_latencychain.png"/></center>

- Latency = Δ1+ Δ2 + Δ3
	- Event 1: Timer expires
	- Event 2: Interrupt handler marks the task to react
	- Event 3: Linux scheduler switches to the task
	- Event 4: Application task begins executing

---
title: Timing Analysis
subtitle: Generalization

<center>
<div style="display:table-cell; width:50%;"><img style="width:400px; height:auto" src="images/timing_states.png"/></div>
<div style="display:table-cell; width:50%; text-align: left; vertical-align: middle">
<ul>
<li>Time between start and end</li>
<li>Time for each transition</li>
<li>Percentage sub-duration vs total</li>
</ul>
</div>
<br/>
</center>

---
title: Timing Analysis
subtitle: Using states

- State machine for timing analysis
	- Implementation in Java as Trace Compass extension

- Data-driven pattern matching (in XML)
	- Defining timing analyses on-the-fly

---
title: Timing Analysis API
subtitle: ISegment

- A segment provides a **start time** and an **end time**
- What that duration means is specific to the analysis that will generate it
- This interface is the basis of the "Timing" family of analysis and views

<center><img src="images/timing_segment.png"/></center>

---
title: Timing Analysis API
subtitle: ISegmentStore

- Stores segments (`ISegment`)
- Extends "well known" Java `Collection` interface
	- `iterator()`, `add()`, `isEmpty()`, etc.
- Adds the notion of intersection: `getIntersectingElements`(start, end)

<center><img src="images/timing_segmentstore.png"/></center>

---
title: Timing Analysis API
subtitle: Limitations

- **WARNING**: Current segment store implementations are loaded **fully into memory**.
- If your trace will generate many segments, Trace Compass might **run out of memory**.

- This will likely be fixed in the near future versions of Trace Compass.


---
title: Timing Analysis API
subtitle: AbstractSegmentStoreAnalysisModule

- Similar to normal analysis but with the notion of segments
- **Builds** segments and **stores** them: `buildAnalysisSegments()`
- Provides the segment store (for views, etc): `getSegmentStore()`

<center><img src="images/timing_segmentanalysis.png"/></center>

---
title: Exercise: Create segment store module

- Reset to **TRACECOMPASS3_START**
- `ProcessingLatencyModule` is created for you with some **TODOS**. plugin.xml is already filled.
	- Populate the list of aspects (columns) to be used by some views. **Hint**: Reused some of the existing classes in the package.
	- Create the analysis request. This class has the responsibility of filling the segment store.
	- Complete the **processEvent** helper method. This should handle events one by one and adds segments to the segment store. Note that we need two event (start and end) so we need to keep track of ongoing ones. 
	- Return all the list of aspects to be used: `Name` and `Content`

---
title: Module 7 Review

- **Segments** (`ISegment`) are defined by a start and an end time. They can represent things like execution times, latencies, etc.
- Multiple segments can represent **latency chain**. For example multiple sub-steps of a process.
- State systems can help generalize the creation of segments
- **ISegmentStore** stores segments like a Java Collection but with interection methods
- **AbstractSegmentStoreAnalysisModule** helps building segments, storing them and providing them to clients (views).
- In the exercise: We have created a **segment-based analysis module** that creates segments and stores them in a segment store which will be available for our views.

---
title: Module 8
subtitle: Timing Analysis Views


---
title: Timing Analysis Views
subtitle: Overview

- Several types of views can be added that make use of segment store analysis
	- Latencies (table)
	- Statistics
	- Scatter chart
	- Density

- Most of those views follow a similar pattern:
	- A abstract viewer to help create the widgets specific to the type of view
	- An abstract view class to help create the container this type of view and that will create the chosen viewer
	- This is similar to Time Graph views VS Time Graph Viewer

---
title: Timing Analysis Views
subtitle: Overview

- Viewers query analysis based on segment stores (see previous module!)

TODO: PICTURE HERE?

---
title: Latency Table view

- The Latency view displays segments in a simple table format.

<center><img src="images/timingviews_latencies.png"/></center>
	(Example based on System Calls analysis)

---
title: Latency Table view
subtitle: API

- `AbstractSegmentStoreTableView`
	- An abstract class that helps create a table view.
	- `createSegmentStoreViewer`: has to return an AbstractSegmentStoreTableViewer

---
title: Latency Table view
subtitle: API

- `AbstractSegmentStoreTableViewer`
	- An abstract class that helps create a table viewer.
	- `createProviderColumns`: can be overidden to have greater influence on columns (order, etc).
	- `getSegmentStoreProvider`: returns which analysis module will provide the segment store
~~~java
@Override
protected ISegmentStoreProvider getSegmentStoreProvider(ITmfTrace trace) {
    return TmfTraceUtils.getAnalysisModuleOfClass(trace, SystemCallLatencyAnalysis.class, SystemCallLatencyAnalysis.ID);
}
~~~

---
title: Exercise: Create a Latency Table

- Reset to **TRACECOMPASS4_START**
- Create class `ProcessingLatencyTableViewer`, select super class (extends)  `AbstractSegmentStoreTableViewer`
	- Implement method `getSegmentStoreProvider`
- In plugin.xml, create the missing class `ProcessingLatencyTableView` (tip: click the hyperlink to bring up the New Class wizard). Select super class (extends)  `AbstractSegmentStoreTableView`.
	- Implement `createSegmentStoreViewer` in `ProcessingLatencyTableView`
- <b>Go!</b>

---
title: Statistics view

- The Statistics view displays statistics for each segment type
	- You can also navigate to the minimum and maximum of each segment type from this view (eg. longest `futex` system call)

<center><img src="images/timingviews_statistics.png"/></center>

---
title: Statistics view
subtitle: API

- `AbstractSegmentStatisticsAnalysis`
	- An abstract class that helps create a statistics module resuing an existing segment store provider (i.e. an other module).
	- `getSegmentType`: returns the segment type to compute the statistics for.
	- `getSegmentProviderAnalysis`: returns an existing segmentstore provider.

~~~java
@Override
protected ISegmentStoreProvider getSegmentProviderAnalysis(ITmfTrace trace) {
    return TmfTraceUtils.getAnalysisModuleOfClass(trace, SystemCallLatencyAnalysis.class, SystemCallLatencyAnalysis.ID);
}
~~~

---
title: Statistics view
subtitle: API

- `AbstractSegmentStoreStatisticsView`
	- An abstract class that helps create a statistics view.
	- `createSegmentStoreStatisticsViewer`: has to return an `AbstractSegmentStoreStatisticsViewer`

- `AbstractSegmentStoreStatisticsViewer`
	- An abstract class that helps create a statistics viewer.
	- `createStatisticsAnalysiModule`: returns which analysis module will provide the statistics.
	- `updateElements`: creates and updates items in the statistics tree. This is where a hierarchy can be created.

---
title: Exercise: Create a Statistics View

- Reset to **TRACECOMPASS5_START**
- Create a class `ProcessingLatencyStatisticsModule` with super class (extends) `AbstractSegmentStatisticsAnalysis`
	- Implement `getSegmentType()`: In our example, it's the name of the segment
	- Implement  `getSegmentProviderAnalysis`
- `ProcessingLatencyStatisticsViewer` is created for you with some **TODOS**.
	- Return a new instance of the statistics module (see previous steps)
	- Build the statistics tree by creating new entries
- In plugin.xml, create the missing class `ProcessingLatencyStatisticsView` (tip: click the hyperlink to bring up the New Class wizard). Select super class `AbstractSegmentStoreStatisticsView`.
- <b>Go!</b>

---
title: Scatter chart

- The Scatther view displays the segment durations over time in a 2D plot chart
	- Each dot reprensent the time it ended on the X-axis and its duration on the Y-axis
	- Makes it possible to spot **outliners**

<center><img src="images/timingviews_scatter.png"/></center>

---
title: Scatter chart
subtitle: API

- `TmfChartView`
	- An abstract class that helps create a view based on a chart (SWTChart)
	- `createChartViewer`: has to return an `TmfXYChartViewer` (which `AbstractSegmentStoreScatterGraphViewer` extends).

- `AbstractSegmentStoreScatterGraphViewer`
	- An abstract class that helps create a scatter viewer.
	- `getSegmentStoreProvider`: returns which analysis module will provide the segment store

---
title: Exercise: Create a Scatter View

- Reset to **TRACECOMPASS6_START**
- Create class `ProcessingLatencyScatterGraphViewer`, select super class (extends)  `AbstractSegmentStoreScatterGraphViewer`
	- Implement method `getSegmentStoreProvider`
- In plugin.xml, create the missing class `ProcessingLatencyScatterView` (tip: click the hyperlink to bring up the New Class wizard). Select super class (extends)  `TmfChartView`.
	- Implement `createChartViewer` 
- <b>Go!</b>

---
title: Density view

- The Density view displays the segment durations on the frenquency domain.
	- Each bar reprensent the **duration** of the segment on the **X-axis** and the **count** of segments on the **Y-axis**
<center><img src="images/timingviews_density.png" style="width:600px"/></center>
<br/>
- In other words, fast system calls are on the left and slow system calls are on the right

---
title: Density view
subtitle: API

- `AbstractSegmentStoreDensityView`
	- An abstract class that helps create a density view
	- `createSegmentStoreTableViewer`: has to return an `AbstractSegmentStoreTableViewer` (can reuse the one from Latency table view!). Left part of the view.
	- `createSegmentStoreDensityViewer`: has to return an `AbstractSegmentStoreDensityViewer`. Right part of the view.

- `AbstractSegmentStoreDensityViewer`
	- An abstract class that helps create a density viewer.
	- `getSegmentStoreProvider`: returns which analysis module will provide the segment

---
title: Exercise: Create a Density View

- Reset to **TRACECOMPASS7_START**
- Create class `ProcessingLatencyDensityViewer`, select super class (extends)  `AbstractSegmentStoreDensityViewer`
	- Implement method `getSegmentStoreProvider`
- In plugin.xml, create the missing class `ProcessingLatencyDensityView` (tip: click the hyperlink to bring up the New Class wizard). Select super class (extends)  `AbstractSegmentStoreDensityView`.
	- Implement `createSegmentStoreTableViewer` : Reuse the one from Latency Table view!
	- Implement `createSegmentStoreDensityViewer`
- <b>Go!</b>

---
title: Module 8 Review

- Many views can be built by reading a **segment store**.
- In the exercises, we have created:
	- **Latency Table** view
	- **Statistics** view
	- **Scatter chart** view
	- **Density** view
- Those views can be generated by follow a similar patter of creating a **viewer inside a view**, and specifying the segment store to use.

---
title: Module 9
subtitle: Custom Analysis

---
title: XML analysis basic
subtitle:
content_class: smaller


- The joys of XML analysis
<br><br>
    - Customize Trace Compass without recompiling
    <br><br>
    - Add custom analysis
    <br><br>
    - Add custom and re-usable views
    <br><br>
    - Share analysis and views
    <br><br>
    - Find an execution flow within the trace    

---
title: XML analysis basic
subtitle: Advanced pattern matching
content_class: smaller

- Find stateful sequence within the trace
<br><br>
<img src="images/xml/general_pattern.png"/>

---
title: XML analysis basic
subtitle: Advanced pattern matching
content_class: smaller

- XML description
<br><br>
<pre class="prettyprint" data-lang="xml">
    &lt;fsm id="process:processing"&gt;
	    &lt;precondition event="ust_master:PROCESS_START"/&gt;
	    &lt;precondition event="ust_master:PROCESS_END"/&gt;
	    &lt;initialState&gt;
		    &lt;transition event="ust_master:PROCESS_INIT" target="INITIALIZING" action="process_init:save_id"/&gt;
	    &lt;/initialState&gt;
	    &lt;state id="INITIALIZING"&gt;
		    &lt;transition event="ust_master:PROCESS_START" cond="test_id" target="PROCESSING" action="process_start"/&gt;
	    &lt;/state&gt;
	    &lt;state id="PROCESSING"&gt;
		    &lt;transition event="ust_master:PROCESS_END" cond="test_id" target="END" action="process_end"/&gt;
	    &lt;/state&gt;
	    &lt;final id="END"/&gt;
    &lt;/fsm&gt;
</pre>

---
title: XML analysis basic
subtitle: Generic views
content_class: smaller

<center>
<div style="display:table-cell; width:50%;"><img style="width:300px; height:auto" src="images/xml/tracecompass_xml_timegraph.png"/></div>
<div style="display:table-cell; width:50%; text-align: center; vertical-align: middle"><span>XML Timegraph View</span></div>
<br/>
<div style="display:table-cell; width:50%;"><img style="width:300px; height:auto" src="images/xml/tracecompass_xml_xy_chart.png"/></div>
<div style="display:table-cell; width:50%; text-align: center; vertical-align: middle"><span>XML XY View</span></div>
<br/>
<div style="display:table-cell; width:50%;"><img style="width:300px; height:auto" src="images/xml/tracecompass_timing_analysis.png"/></div>
<div style="display:table-cell; width:50%; text-align: center; vertical-align: middle"><span>Timing analysis on-the-fly</span></div>
</center>

---
title: How do we use an XML analysis?
subtitle:
content_class: smaller

<center>
<div style="display:table-cell; width:50%; text-align: center; vertical-align: middle"><span>Define the analysis</span></div>
<div style="display:table-cell; width:50%;"><img style="width:300px; height:auto" src="images/xml/design_xml.png"/></div>
<br/>
<div style="display:table-cell; width:50%; text-align: center; vertical-align: middle"><span>Import an XML analysis</span></div>
<div style="display:table-cell; width:50%;"><img style="width:300px; height:auto" src="images/xml/manage_xml_analysis.png"/></div>
<br/>
<div style="display:table-cell; width:50%; text-align: center; vertical-align: middle"><span>Analyze result in Trace Compass</span></div>
<br/>
</center>

---
title: How do we define XML analysis?
subtitle:
content_class: smaller

- Design structure

---
title: Example 1
subtitle:
content_class: smaller

<br><br><br><br>
**Your first XML analysis**

---
title: Example 1
subtitle: Importing the XML analysis
content_class: smaller

- Reset to commit **blabla**
- In the project explorer,
    - Expand the tracing project
    - Right-click the Traces folder
    - Select `Manage XML analyses...`
    - In the opened dialog import the `training-example-full-states.xml` file and close the dialog.
- The 'Processing Analysis' analysis is now installed
- The analysis should be present under the trace 'master_player-14408-20161020-144931'

---
title: Example 1
subtitle: Importing the XML analysis
content_class: smaller

<img src="images/xml/ManageXMLAnalysis.png"/>

---
title: Example 1
subtitle: Execute the analysis
content_class: smaller

- Open the trace.
    The 'Xml kernel State System' analysis should be now expandable.

<div style="float:right;"><img src="images/xml/analysis_and_view_under_trace.png" style="width:250px;"/></div>

<ul>
<li> Expand the analysis. Several views are present under it:</li>
<ul>
    <li> 'Latency statistics' </li>
    <li> 'Latency Table'</li>
    <li> 'Processing States XML' </li>
    <li> ... </li>
</ul>
</ul>
<br>

- Open the view named `Processing States XML`

---
title: Example 1
subtitle: Observe the analysis
content_class: smaller

- A timegraph view opens and is `populated`
    <br><br>
- some `entries (rows) are empty`. Why?

<img src="images/xml/empty_entry.png"/>
<br>
**The state system is probably not well designed**
<br><br>
<br><br>

Next slide: viewing the XML file

---
title: Example 1
subtitle: Edit the analysis
content_class: smaller

- Reopen the 'Manage XML analyses...' dialog (seen previously)
- Select the 'training-example-full-states.xml' file and click on the 'Edit' button

<img src="images/xml/edit_button.png"/>

---
title: Example 1
subtitle: Edit the analysis
content_class: smaller

The XML file opens in an editor
<br>

- We can see that there is few <code>&lt;stateChange&gt;</code> where the  <code>&lt;stateValue&gt;</code> is set to **null**.
<pre class="prettyprint" data-lang="xml">
&lt;stateValue type="null" /&gt;
</pre>

    <br><br>
- We probably don't want to set the value to **null** for the <code>ust_master:PROCESS_INIT</code> and <code>ust_master:PROCESS_START</code> events.
<br><br>
Next slide: editing the XML file

---
title: Example 1
subtitle: Edit the analysis
content_class: smaller

- Change the state value for event <code>ust_master:PROCESS_INIT</code> to <code>INITIALIZING</code>
<pre class="prettyprint" data-lang="xml">
    &lt;stateValue type="int" value="$INITIALIZING"/&gt;
</pre>
<br>
- Change the state value for event <code>ust_master:PROCESS_START</code> to <code>PROCESSING</code>
<pre class="prettyprint" data-lang="xml">
    &lt;stateValue type="int" value="$PROCESSING"/&gt;
</pre>
<br>
- Save the file. The opened trace should close. 
<br>
- Reopen the trace and the view
<br>

---
title: Example 1
subtitle: Edit the analysis
content_class: smaller

<img src="images/xml/filled_entries.png"/>

- The view is populated. There is **no empty entry**

---
title: Example 1
subtitle: Recap
content_class: smaller

- We've learned how to `import an XML analysis`
<br><br>
- We've learned how to `execute the analysis` and analyze the data
<br><br>
- We've learned how to `edit the analysis`

---
title: Example 2
subtitle:
content_class: smaller

**Timing analysis**

---
title: Example 2
subtitle:
content_class: smaller

- Reset to commit **blabla**
<br><br>
- Import the 'training-example-processing-timing.xml' file

<img src="images/xml/manager_timing_analysis.png"/>

- The 'Processing Latency XML' analysis should be present under the trace
<br><br>

---
title: Example 2
subtitle:
content_class: smaller

- Reopen The trace
    - Several views are now present under the analysis.
    
<img src="images/xml/latency_view_label.png"/>

<br/>

- Open the latency views:
    - Latency Statistcis view
    - Latency Table view
    - Latency vs Count
    - Latency vs Time

---
title: Example 2
subtitle: Observe the analysis
content_class: smaller

- All the views are empty
<br><br>
**The analysis probably does not create any latency data**
<br><br>
<br><br>

Next slide: viewing the XML file

---
title: Example 2
subtitle: Edit the analysis
content_class: smaller

- Open the file in an editor
- The file contains an action that creates latency data (segments) in the file

<pre class="prettyprint" data-lang="xml">
    &ltaction id="processing_endeded">
        &ltsegment&gt
          &ltsegType segName="PROCESSING" /&gt
          &ltsegContent&gt
            &ltsegField name="requester" type="string"&gt
              &ltstateValue type="eventField" value="requester" /&gt
            &lt/segField&gt
            &ltsegField name="id" type="string"&gt
              &ltstateValue type="eventField" value="id" /&gt
            &lt/segField&gt
          &lt/segContent&gt
        &lt/segment&gt
      &lt/action&gt
</pre>
**This action is never used**
<br>
- Next slide: editing the XML file

---
title: Example 2
subtitle: Edit the analysis
content_class: smaller

- We need to call the action when the processing endeded (when we receive the `ust_master:PROCESS_END`event).
<br><br>
- Let's add an action to the `ust_master:PROCESS_END` event transition.
<br>
<pre class="prettyprint" data-lang="xml">
&lt;transition event="ust_master:PROCESS_END" target="end" cond="cond_same_data" action="processing_endeded" /&gt;
</pre>
<br><br>
- Save the file. The opened trace should close. 
<br><br>
- Reopen the trace and the latency views
<br><br>
- The views are now **populated**.
<br><br>
- The same latency views and content as the JAVA one

---
title: Example 2
subtitle: Analysis result
content_class: smaller

<img src="images/xml/latency_views_populated.png"/>

---
title: Example 2
subtitle: Recap
content_class: smaller

- We've learned how to `generate latencies data` from the XML analysis
<br><br>
- We've learned how to `analyze latencies` based on XML analysis

---
title: Training recap
subtitle: what we've seen
content_class: smaller

- We've learned how to `import an XML analysis`
<br><br>
- We've learned how to `execute the analysis` and analyze the data
<br><br>
- We've learned how to `edit the analysis
<br><br>
- We've learned how to `generate latencies data` from the XML analysis
<br><br>
- We've learned how to `analyze latencies` based on XML analysis
