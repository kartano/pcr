# PCR

The PCR system is a web-based patient care record system designed with smaller to mid-sized first aid or first responder organizations.  System design is around BLS providers with some additional ALS PCR provisions also allowed, depending on the particular needs of the implementing orgnaization.

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt).

## Table of Contents

- [Background](#background)
- [Installation])(#installation)
  - [Server Installation](#server-installation)
  - [Client Installation](#client-installation)
- [Usage](#usage)
  - [Responder](#responder)
  - [Administrator](#administrator)
  - [Systems Administrator](@systems-administrator)
- [Maintainers](#maintainers)
- [Contributing](#contributing)
  - [Contributors](#contributors)
- [License](#license)

## Background

The system is designed to fulfill the smaller first aid/non-profit first responder environment by removing a lot of what would be confusing and unnecessary information collection.  First aiders, non-profit first responders or even places of learning rarely - if ever - need to collect information such as insurance, a casualty's SSN, or to record extensive information pertaining to diagnosis from resources such as a 12-lead or 4-lead EKG monitor.

The design goal is to develop a system which is:
* Secure;
* Easy to use and as intuitive as possible;
* Flexible;
* More resourceful for administrators than traditional paper-based PCRs (statistics, patient breakdowns, allowing better planning for resources for events or locations in futuire, etc);
* To be organization agnostic (any organization using the system should be able to configure requirements on charts from units of measurement to enforcing additional polcy);
* That the software should function well on any device from desktop machines, laptops to tablets; and
* That local applications should also be able to be written using any available language that can consiume RESTful APIs.

The system is also designed to allow for stand-alone servers in disperate locations, or to be centralized (I.E: with load balancers in an AWS environment).

### Version Control

Individual PCRs are held within the system using a version control paradigm equivalent to that of GIT.

### Patient Care Records

Patient care records can be either:
* Created by a central dispatch center; or
* Created by responders in-field.

Workflow for a PCR in either case is as follows:

1. A PCR is either "checked-out" by a response crew, or it is created as a blank PCR by that crew en situ (I.E: a response team attends an accident or incident whilst traveling to or from a specific event or post).  A PCR that is "checked-out" will be left with a read-only lock for other responders or administrators and the crew who has taken ownership of that PCR are the ONLY crew who may change it.
2. Any changes made to the checked out PCR are effectively "pushed" to their local copy of that PCR.
3. The response crew will "commit" their PCR back to the system once completed.
4. A PCR MUST NOT be able to be changed once committed.  A PCR MAY have appendices added to them by either the responders who commited it, or by a higher level user.

The likely workflow for handling PCRs once committed is:

1.  Any original data forming part of a committed PCR MUST remain unalterable.  
2.  A PCR MAY have addenda added to them.  An addendum MUST be created by either the responder who committed the PCR, or by somebody with a higher level of access.
3.  A PCR MUST NOT be able to be given to another party (a casualty copy, a handover copy to a team with a higher SOP, copies of event PCRs to event organizers etc) until that PCR has been committed (half-completed PCRs MUST NOT be given to any party).
4.  A PCR that has been committed MAY be viewed as read-only, but MUST only be accessible by the filling responders OR by a higher level administer.
5.  Any PCR exported to an event or client MUST have ALL identifiable information regarding a casualty removed or redacted.
6.  Any data sent from a client or off the web MUST be encrypted (SSL etc).

## Installation

TO DO:  Write down installation notes for installation a new system.  Write detailled notes on installation a development server.

### Software Requirements

TO DO:  List software and packages required to install at least the back end server.

### Server Installation

TO DO:  List required software.

TO DO:  Notes pertaining to requirements to run the server portion of the system will go here.

### Client Installation

TO DO:  Notes pertaining to any client-based software will go here.

## Usage

It is envisaged that thorough user documentation will be written once the system advances to at least an alpha stage.

### Responder

TO DO: Notes pertaining to system use and mechanics for a typical responder will go here.

### Administrator

TO DO:  Notes pertaining to higher level organization administrators will go here.

### Systems Administrator

TO DO:  Notes pertaining to system maintenance, backups, updates and such will go here.

## Maintainers

* [@Simon Mitchell](https://github.com/kartano)
* [@CyberJosie](https://github.com/CyberJosie).

## Contributing

We welcome any and all feedback on this project.  A link will be provided once we have a location for tracking such tickets available.

### Contributors

This project exists thanks to all the people who contribute. 

## Thanks

*  [St John Amnbulance Mildura](https://www.facebook.com/StJohnMildura/).

## License

[MIT](LICENSE)
