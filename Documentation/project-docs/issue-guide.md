Issue Guide
===========

This page outlines how the CoreFx team thinks about and handles issues.  For us, issues on GitHub represent actionable work that should be done at some future point.  It may be as simple as a small product or test bug or as large as the work tracking the design of a new feature.  However, it should be work that falls under the charter of CoreFx, which is a collection of foundational libraries that make up the .NET Core development stack.  We will keep issues open even if the CoreFx team internally has no plans to address them in an upcoming release, as long as we consider the issue to fall under our purview.

### When we close issues
As noted above, we don't close issues just because we don't plan to address them in an upcoming release.  So why do we close issues?  There are few major reasons:

1. Issues unrelated to CoreFx.  When possible, we'll try to find a better home for the issue and point you to it.
2. Cross cutting work better suited for another team.  Sometimes the line between the framework, languages and runtime blurs.  For some issues, we may feel that the work is better suited for the runtime team, language team or other partner.  In these cases, we'll close the issue and open it with the partner team.  If they end up not deciding to take on the issue, we can reconsider it here.
3. Nebulous and Large open issues.  Large open issues are sometimes better suited for [User Voice](http://visualstudio.uservoice.com/forums/121579-visual-studio/category/31481--net), especially when the work will cross the boundaries of the framework, language and runtime.  A good example of this is the SIMD support we recently added to CoreFx.  This started as a [User Voice request](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/suggestions/2212443-c-and-simd), and eventually turned into work for both the core libraries and runtime.

Sometimes after debate, we'll decide an issue isn't a good fit for CoreFx.  In that case, we'll also close it.  Because of this, we ask that you don't start working on an issue until it's tagged with [up-for-grabs](https://github.com/dotnet/corefx/labels/up-for-grabs) or [api-approved](https://github.com/dotnet/corefx/labels/api-approved).  Both you and the team will be unhappy if you spend time and effort working on a change we'll ultimately be unable to take. We try to avoid that.

### Labels
We use GitHub [labels](https://github.com/dotnet/corefx/labels) on our issues in order to classify them.  We have the following categories per issue:
* **Area**: These area-&#42; labels (e.g. [area-System.Collections](https://github.com/dotnet/corefx/labels/area-System.Collections)) call out the assembly or assemblies the issue applies to. In addition to labels per assembly, we have a few other area labels: [area-Infrastructure](https://github.com/dotnet/corefx/labels/area-Infrastructure), for issues that relate to our build or test infrastructure, and [area-Meta](https://github.com/dotnet/corefx/labels/area-Meta) for issues that deal with the repository itself, the direction of the .NET Core Platform, our processes, etc. See [full list of areas](#areas).
* **Issue Type**: These labels classify the type of issue.  We use the following types:
  * [bug](https://github.com/dotnet/corefx/labels/bug): Bugs in an assembly.
  * api-&#42; ([api-approved](https://github.com/dotnet/corefx/labels/api-approved), [api-needs-work](https://github.com/dotnet/corefx/labels/api-needs-work), [api-ready-for-review](https://github.com/dotnet/corefx/labels/api-ready-for-review)): Issues which would add APIs to an assembly (see [API Review process](api-review-process.md) for details).
  * [enhancement](https://github.com/dotnet/corefx/labels/enhancement): Improvements to an assembly which do not add new APIs (e.g. performance improvements, code cleanup).
  * [test bug](https://github.com/dotnet/corefx/labels/test%20bug): Bugs in the tests for a specific assembly.
  * [test enhancement](https://github.com/dotnet/corefx/labels/test%20enhancement): Improvements in the tests for a specific assembly (e.g. improving test coverage).
  * [documentation](https://github.com/dotnet/corefx/labels/documentation): Issues related to documentation (e.g. incorrect documentation, enhancement requests).
  * [question](https://github.com/dotnet/corefx/labels/question): Questions about the product, source code, etc.
* **Other**:
  * [up-for-grabs](https://github.com/dotnet/corefx/labels/up-for-grabs): Small sections of work which we believe are well scoped.  These sorts of issues are a good place to start if you are new.  Anyone is free to work on these issues.
  * [needs more info](https://github.com/dotnet/corefx/labels/needs%20more%20info): Issues which need more information to be actionable.  Usually this will be because we can't reproduce a reported bug.  We'll close these issues after a little bit if we haven't gotten actionable information, but we welcome folks who have acquired more information to reopen the issue.

In addition to the above, we have a handful of other labels we use to help classify our issues.  Some of these tag cross cutting concerns (e.g. [tenet-performance](https://github.com/dotnet/corefx/labels/tenet-performance)), whereas others are used to help us track additional work needed before closing an issue (e.g. [api-needs-exposed](https://github.com/dotnet/corefx/labels/api-needs-exposed)).

### Milestones
We use [milestones](https://github.com/dotnet/corefx/milestones) to prioritize work for each upcoming release to NuGet.org.

### Assignee
We assign each issue to assignee, when the assignee is ready to pick up the work and start working on it.  If the issue is not assigned to anyone and you want to pick it up, please say so - we will assign the issue to you.  If the issue is already assigned to someone, please coordinate with the assignee before you start working on it.

Note: This is a new scheme introduced in 2016/9.  The old scheme used assignees as area owners.  We will migrate issues to the new scheme throughout 2016.

### Areas
Areas are tracked by labels area-&#42; (e.g. area-System.Collections). Each area typically corresponds to one or more contract assemblies.

| Area                                                                                          | Owners / experts | Description |
|-----------------------------------------------------------------------------------------------|------------------|-------------|
| [area-Infrastructure](https://github.com/dotnet/corefx/labels/area-Infrastructure)                      | [@mellinoe](https://github.com/mellinoe), [@ericstj](https://github.com/ericstj), [@weshaggard](https://github.com/weshaggard) |Covers:<ul><li>Packaging</li><li>Build and test infra for CoreFX repo</li><li>VS integration</li></ul><br/>**Triage in progress** |
| [area-Meta](https://github.com/dotnet/corefx/labels/area-Meta)                                | [@tarekgh](https://github.com/tarekgh) | Issues without clear association to any specific API/contract, e.g. <ul><li>new contract proposals</li><li>cross-cutting code/test pattern changes (e.g. FxCop failures)</li><li>project-wide docs</li></ul><br/>**Triage in progress** |
| [area-Serialization](https://github.com/dotnet/corefx/labels/area-Serialization)              | [@shmao](https://github.com/shmao), [@zhenlan](https://github.com/zhenlan) | Packages:<ul><li>System.Runtime.Serialization.Xml</li><li>System.Runtime.Serialization.Json</li><li>System.Private.DataContractSerialization</li><li>System.Xml.XmlSerialization</li></ul> Excluded:<ul><li>System.Runtime.Serialization.Formatters</li></ul> |
| **System contract assemblies** | | |
| [System.AppContext](https://github.com/dotnet/corefx/labels/area-System.AppContext)           | [@AlexGhiondea](https://github.com/AlexGhiondea) |  |  |
| [System.Buffers](https://github.com/dotnet/corefx/labels/area-System.Buffers)                 | [@alexperovich](https://github.com/alexperovich), [@safern](https://github.com/safern) |  |
| [System.CodeDom](https://github.com/dotnet/corefx/labels/area-System.CodeDom)                 | [@Priya91](https://github.com/Priya91) |  |
| [System.Collections](https://github.com/dotnet/corefx/labels/area-System.Collections)         | [@ianhays](https://github.com/ianhays), [@safern](https://github.com/safern) | </ul>Excluded:<ul><li>System.Array -> System.Runtime</li></ul> |
| [System.ComponentModel](https://github.com/dotnet/corefx/labels/area-System.ComponentModel)   |  [@safern](https://github.com/safern), [@AlexGhiondea](https://github.com/AlexGhiondea) |  |
| [System.ComponentModel.DataAnnotations](https://github.com/dotnet/corefx/labels/area-System.ComponentModel.DataAnnotations) | [@lajones](https://github.com/lajones), [@divega](https://github.com/divega), [@ajcvickers](https://github.com/ajcvickers) | **Triage in progress** |
| [System.Composition](https://github.com/dotnet/corefx/labels/area-System.Composition)         | [@AlexGhiondea](https://github.com/AlexGhiondea) |  |
| [System.Configuration](https://github.com/dotnet/corefx/labels/area-System.Configuration)     | [@JeremyKuhne](https://github.com/JeremyKuhne) |  |
| [System.Console](https://github.com/dotnet/corefx/labels/area-System.Console)                 | [@ianhays](https://github.com/ianhays) |  |
| [System.Data](https://github.com/dotnet/corefx/labels/area-System.Data)                       | [@saurabh500](https://github.com/saurabh500), [@corivera](https://github.com/corivera) |  |
| [System.Data.SqlClient](https://github.com/dotnet/corefx/labels/area-System.Data.SqlClient)   | [@saurabh500](https://github.com/saurabh500), [@YoungGah](https://github.com/YoungGah) | **Pending triage** |
| [System.Diagnostics](https://github.com/dotnet/corefx/labels/area-System.Diagnostics)         | [@joperezr](https://github.com/dotnet/joperezr) |  |
| [System.Diagnostics.Process](https://github.com/dotnet/corefx/labels/area-System.Diagnostics.Process) | [@Priya91](https://github.com/Priya91) |  |
| [System.Diagnostics.Tracing](https://github.com/dotnet/corefx/labels/area-System.Diagnostics.Tracing) |  [@brianrob](https://github.com/brianrob), [@vancem](https://github.com/vancem), [@valenis](https://github.com/valenis)| Packages:<ul><li>System.Diagnostics.DiagnosticSource</li><li>System.Diagnostics.PerformanceCounter</li><li>System.Diagnostics.Tracing</li><li>System.Diagnostics.TraceSource</li></ul><br/>**Pending triage** |
| [System.DirectoryServices](https://github.com/dotnet/corefx/labels/area-System.DirectoryServices) | [@tquerec](https://github.com/tquerec) |  |
| [System.Drawing](https://github.com/dotnet/corefx/labels/area-System.Drawing)                 | [@alexperovich](https://github.com/alexperovich) |  |
| [System.Dynamic.Runtime](https://github.com/dotnet/corefx/labels/area-System.Dynamic.Runtime) | [@VSadov](https://github.com/VSadov), [@OmarTawfik](https://github.com/OmarTawfik) |  |
| [System.Globalization](https://github.com/dotnet/corefx/labels/area-System.Globalization)     | [@krwq](https://github.com/krwq), [@tarekgh](https://github.com/tarekgh) |  |
| [System.IO](https://github.com/dotnet/corefx/labels/area-System.IO)                           | [@JeremyKuhne](https://github.com/JeremyKuhne), [@ianhays](https://github.com/ianhays) |  |
| [System.IO.Compression](https://github.com/dotnet/corefx/labels/area-System.IO.Compression)   | [@ianhays](https://github.com/ianhays) |  |
| [System.Linq](https://github.com/dotnet/corefx/labels/area-System.Linq)                       | [@VSadov](https://github.com/VSadov), [@OmarTawfik](https://github.com/OmarTawfik) |  |
| [System.Linq.Expressions](https://github.com/dotnet/corefx/labels/area-System.Linq.Expressions)   | [@VSadov](https://github.com/VSadov), [@OmarTawfik](https://github.com/OmarTawfik) |  |
| [System.Linq.Parallel](https://github.com/dotnet/corefx/labels/area-System.Linq.Parallel)     | [@alexperovich](https://github.com/alexperovich), [@kouvel](https://github.com/kouvel) |  |
| [System.Memory](https://github.com/dotnet/corefx/labels/area-System.Memory)                   | [@KrzysztofCwalina](https://github.com/KrzysztofCwalina), [@ahsonkhan](https://github.com/ahsonkhan), [@shiftylogic](https://github.com/shiftylogic) | **Pending triage** |
| [System.Net](https://github.com/dotnet/corefx/labels/area-System.Net)                         | [@davidsh](https://github.com/davidsh), [@CIPop](https://github.com/CIPop), [@Priya91](https://github.com/Priya91) | **Triage in progress** |
| [System.Net.Http](https://github.com/dotnet/corefx/labels/area-System.Net.Http)               | [@davidsh](https://github.com/davidsh), [@CIPop](https://github.com/CIPop), [@Priya91](https://github.com/Priya91) | |
| [System.Net.Security](https://github.com/dotnet/corefx/labels/area-System.Net.Security)       | [@davidsh](https://github.com/davidsh), [@CIPop](https://github.com/CIPop), [@Priya91](https://github.com/Priya91) | |
| [System.Net.Sockets](https://github.com/dotnet/corefx/labels/area-System.Net.Sockets)         | [@davidsh](https://github.com/davidsh), [@CIPop](https://github.com/CIPop), [@Priya91](https://github.com/Priya91) | |
| [System.Numerics](https://github.com/dotnet/corefx/labels/area-System.Numerics)               | [@mellinoe](https://github.com/mellinoe) |  |
| [System.Reflection](https://github.com/dotnet/corefx/labels/area-System.Reflection)           | [@dnlharvey](https://github.com/dnlharvey), [@AtsushiKan](https://github.com/AtsushiKan) |  |
| [System.Reflection.Emit](https://github.com/dotnet/corefx/labels/area-System.Reflection.Emit) | [@dnlharvey](https://github.com/dnlharvey), [@AtsushiKan](https://github.com/AtsushiKan) |  |
| [System.Reflection.Metadata](https://github.com/dotnet/corefx/labels/area-System.Reflection.Metadata) | [@tmat](https://github.com/tmat), [@nguerrera](https://github.com/nguerrera) |  |
| [System.Resources](https://github.com/dotnet/corefx/labels/area-System.Resources)             | [@ramarag](https://github.com/ramarag), [@tarekgh](https://github.com/tarekgh) | **Triage in progress** |
| [System.Runtime](https://github.com/dotnet/corefx/labels/area-System.Runtime)                 | [@AlexGhiondea](https://github.com/AlexGhiondea), [@joperezr](https://github.com/dotnet/joperezr) | Included:<ul><li>System.Runtime.Serialization.Formatters</li><li>System.Runtime.InteropServices.RuntimeInfo</li><li>System.Array</li></ul>Excluded:<ul><li>Path -> System.IO</li><li>StopWatch -> System.Diagnostics</li><li>WebUtility -> System.Net</li></ul> |
| [System.Runtime.CompilerServices](https://github.com/dotnet/corefx/labels/area-System.Runtime.CompilerServices)   | [@AlexGhiondea](https://github.com/AlexGhiondea), [@joperezr](https://github.com/dotnet/joperezr) |  |
| [System.Runtime.Extensions](https://github.com/dotnet/corefx/labels/area-System.Runtime.Extensions)   | [@AlexGhiondea](https://github.com/AlexGhiondea), [@joperezr](https://github.com/dotnet/joperezr) | **Triage in progress** |
| [System.Runtime.InteropServices](https://github.com/dotnet/corefx/labels/area-System.Runtime.InteropServices) | [@tijoytom](https://github.com/tijoytom), [@yizhang82](https://github.com/yizhang82) | Excluded:<ul><li>System.Runtime.InteropServices.RuntimeInfo</li></ul> |
| [System.Security](https://github.com/dotnet/corefx/labels/area-System.Security)               | [@bartonjs](https://github.com/bartonjs), [@steveharter](https://github.com/steveharter) |  |
| System.ServiceModel                                                                           | N/A | [dotnet/wcf](https://github.com/dotnet/wcf) |
| [System.ServiceProcess](https://github.com/dotnet/corefx/labels/area-System.ServiceProcess)   | [@Priya91](https://github.com/Priya91) |  |
| [System.Text.Encoding](https://github.com/dotnet/corefx/labels/area-System.Text.Encoding)     | [@krwq](https://github.com/krwq), [@tarekgh](https://github.com/tarekgh) | Included:<ul><li>System.Text.Encoding**s**.Web</li></ul> |
| [System.Text.RegularExpressions](https://github.com/dotnet/corefx/labels/area-System.Text.RegularExpressions) | [@Priya91](https://github.com/Priya91) |  |
| [System.Threading](https://github.com/dotnet/corefx/labels/area-System.Threading)             | [@kouvel](https://github.com/kouvel), [@alexperovich](https://github.com/alexperovich) |  |
| [System.Transactions](https://github.com/dotnet/corefx/labels/area-System.Transactions)       | [@jimcarley](https://github.com/jimcarley), [@qizhanMS](https://github.com/qizhanMS), [@dmetzgar](https://github.com/dmetzgar) |  |
| [System.Xml](https://github.com/dotnet/corefx/labels/area-System.Xml)                         | [@sepidehMS](https://github.com/sepidehMS), [@krwq](https://github.com/krwq) |  |
| **Microsoft contract assemblies** | | |
| [Microsoft.CSharp](https://github.com/dotnet/corefx/labels/area-Microsoft.CSharp)             | [@VSadov](https://github.com/VSadov), [@OmarTawfik](https://github.com/OmarTawfik) |  |
| [Microsoft.VisualBasic](https://github.com/dotnet/corefx/labels/area-Microsoft.VisualBasic)   | [@VSadov](https://github.com/VSadov), [@OmarTawfik](https://github.com/OmarTawfik) |  |
| [Microsoft.Win32](https://github.com/dotnet/corefx/labels/area-Microsoft.Win32)               | [@sepidehMS](https://github.com/sepidehMS) |  |


Note: Area triage will apply the new scheme (issue types and assignee) throughout 2016.

### Triage rules - simplified

1. Each issue has exactly one **area-&#42;** label
1. Issue has no **Assignee**, unless someone is working on the issue at the moment
1. Use **up-for-grabs** as much as possible, ideally with a quick note about next steps / complexity of the issue
1. Set milestone to **Future**, unless you can 95%-commit you can fund the issue in specific milestone
1. Each issue has exactly one "*issue type*" label (**bug**, **enhancement**, **api-needs-work**, **test bug**, **test enhancement**, **question**, **documentation**, etc.)
1. Don't be afraid to say no, or close issues - just explain why and be polite
1. Don't be afraid to be wrong - just be flexible when new information appears

Feel free to use other labels if it helps your triage efforts (e.g. **needs more info**, **Design Discussion**, **blocked**, **blocking-partner**, **tenet-performance**, **tenet-compatibility**, **os-linux**/**os-windows**/**os-mac-os-x**/**os-unsupported**, **os-windows-uwp**/**os-windows-wsl**, **arch-arm32**/**arch-arm64**)

#### Motivation for triage rules

1. Each issue has exactly one **area-&#42;** label
    * Motivation: Issues with multiple areas have loose responbility (everyone blames the other side) and issues are double counted in reports.
1. Issue has no **Assignee**, unless someone is working on the issue at the moment
    * Motivation: Observation is that contributors are less likely to grab assigned issues, no matter what the repo rules say.
1. Use **up-for-grabs** as much as possible, ideally with a quick note about next steps / complexity of the issue
    * Note: Per http://up-for-grabs.net, such issues should be no longer than few nights' worth of work. They should be actionable (i.e. no misterious CI failures or UWP issues that can't be tested in the open).
1. Set milestone to **Future**, unless you can 95%-commit you can fund the issue in specific milestone
    * Motivation: Helps communicate desire/timeline to community. Can spark further priority/impact discussion.
1. Each issue has exactly one "*issue type*" label (**bug**, **enhancement**, **api-needs-work**, **test bug**, **test enhancement**, **question**, **documentation**, etc.)
    * Don't be afraid to be wrong when deciding 'bug' vs. 'test bug' (flip a coin if you must). The most useful values for tracking are 'api-&#42;' vs. 'enhancement', 'question', and 'documentation'.
1. Don't be afraid to say no, or close issues - just explain why and be polite
1. Don't be afraid to be wrong - just be flexible when new information appears
