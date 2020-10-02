---
layout: default
---

# Reactive Design Principles for Edge Native Applications

## What is an Edge Native application?

With the advent of more and more programmable devices around us, we find ourselves being supported by and collaborating with programs and machines, be that in our homes, in public spaces, or at work. Many of these interactions are local in nature. Some are personal, such as controlling smart home equipment or checking into a hotel, using your phone for everything including unlocking your room. Others have become an integral part of doing business such as attaching the manifest and order information to goods, registering them at each transportation or processing step, and possibly in the future exchanging payment and invoice to locally conclude a deal. Making these interactions dependable requires independence from  faraway components or even the availability of an Internet connection — it must suffice for two edge devices to momentarily communicate with one another.

This basic principle is what defines Edge Native applications: they are created for use-cases whose essential characteristics are local and they are expected to be resilient and work as reliably as a door handle. They are thus only loosely coupled to global or central infrastructure and continue to function under adverse conditions; these are precisely the same qualities that allowed humankind to develop all the astonishing achievements we mostly take for granted today. Edge Native applications continue this line by focusing on the utmost resilience.

## How does Edge Native relate to Cloud Native or IoT?

The definition of Edge Native given above sets a strong focus on the autonomy afforded by programmable edge devices, it is thus intended as a clear delineation from other approaches that include central components. Cloud Native applications make good use of the reliable offering of centrally managed and deployed services within the environment specifically created to this end by cloud data centers. Where reasonable and affordable, this environment can be replicated on-site, with the same benefits, but also with the same drawback in terms of local autonomy: the function of individual devices hinges upon the reachability and availability of central components. Where such a single point of failure is unacceptable, Edge Native provides the answer.

The structure of IoT deployments today is rooted in a cloud-based architecture as well, where edge devices perform only limited processing while the focal point for data collection and decision making is centralized. This is usually achieved by deploying a broker within the local network — presenting straight-forward service discovery as well as a single point of failure — and having that broker connect to a Cloud Native application; it can, therefore, be characterized as Cloud Native with outposts. This shares the same characteristic of centralization with Cloud Native that distinguishes this approach from the uncompromising resilience required by true Edge Native applications.

In general, Edge Native applications do not require any central component, not even a centrally provided network infrastructure. They still work when all they can do is reach physically neighboring devices via local radio connections like Bluetooth, Zigbee, or ultra-wideband (UWB). Since this is a significant restriction, Edge Native applications will often be complemented by Cloud Native or IoT applications for those parts of the overall system functionality that do not require local resilience or that naturally belong to the cloud.

## Edge Native imposes constraints on design and implementation

It lies in the nature of Edge Native applications that the programmer cannot rely upon several common approaches employed in classical desktop applications or cloud services. In particular:
The application’s resources are limited to what the hosting edge device can offer; additional resources for processing and storage may only be contracted from network peers once suitable decentralized services are locally reachable.

- A consistent worldview spanning more than the currently visible devices is unattainable, and even locally it can be forbiddingly expensive to form consensus among larger groups of devices.
- Communication between devices allows for unreliable and possibly slow network links, for example in mesh networks with multiple hops. While better reliability is attainable in some situations, the system would be fragile if it was built on the assumption of reliable and fast communication.
- Devices can fail or be restarted at any time, or the application may be temporarily suspended to give resources to another one.
- Devices can move between different locations or local networks, for example, because they are mounted on vehicles or movable goods; this may make them unreachable from previously joined networks.

Due to the points above, all communication partners need to be treated as temporarily connected only; this will become increasingly relevant as intelligent edge devices form denser networks and their usage becomes more flexible and mobile.

From these constraints, it follows that Edge Native applications are built on a programming model that acknowledges the fact that decisions must be based on the incomplete information that is locally available, and therefore, might need to be revised later if they are recognized as faulty.

Much of the effort in creating Edge Native applications goes into the proper design of communication protocols between different apps as well as between instances of the same application on multiple devices. The flow of information needs to be shaped such that the aforementioned programming model can indeed allow the best possible decisions to be made with local knowledge, keeping in mind potential conflicts to be detected and remedied.

The resilience in Edge Native applications is achieved by a higher degree of redundancy, the same information is replicated on many devices to allow timely usage in the face of unreliable communication.  This principle successfully works in all  biological systems, down to the DNA. 

It is also often helpful to run the same inference algorithms multiple times, wherever they are needed, instead of relying on a single location and spreading the results; this mirrors the simultaneous observation and analysis of a traffic situation by all involved car drivers.

As such, these constraints bring the creation of Edge Native application closer to how we would think about formulating processes among groups of humans, taking away some of the convenient higher-level abstractions we are used to in the cloud and making the design more tangible.

## Edge Native applications need to be Reactive

The [Reactive Manifesto](https://reactivemanifesto.org) was written in 2013 with Cloud Native applications in mind; its main point was to acknowledge that we need a truly distributed application design in order to realize the gains offered by cloud infrastructure. The core tenets of responsiveness and resilience directly apply to Edge Native applications as well, which are naturally message-driven, while elasticity plays a different role: due to their local nature and their focus on peer-to-peer communication Edge Native applications are inherently scalable — even globally — as long as the locally necessary information for taking decisions fits on each host device.

Since many of the core principles and design patterns of Reactive Systems have a strong relationship to distributed systems and Edge Native applications are the ultimate form of distributed computing, it comes as no surprise that the [Reactive Principles](https://principles.reactive.foundation/) inherently apply to them as well.

## Impedance matching between Edge Native and Cloud Native applications

Our greatest achievements in providing complex cloud services in a reliable fashion will need to be matched with Edge Native applications that provide ultimately resilient local services. For this to succeed we must avoid an impedance mismatch between these two quite different software environments: the integration and information flow between edge and cloud needs to be straightforward so that it can be dependable as well.

To this end, the innate confluence of the constraints and principles for Reactive Cloud Native and Reactive Edge Native applications  is extremely fortunate. Both classes of applications:

- Are built from autonomous components. 
- Accept failure, uncertainty, and inconsistency to retain responsiveness.
- Decouple components in space and time.

The patterns of communicating self-contained facts and designing dataflow elegantly bridge the gap between them.

In summary, Edge Native applications need to be Reactive, perhaps even more so than Cloud Native applications, and both of these profit from the symbiosis afforded by this common foundation.
