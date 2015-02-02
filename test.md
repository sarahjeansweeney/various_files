January 22, 2015
Picking up where we left off last week:

Communication:

Meetings
Who needs to communicate with who
Who is responsible for documentation and where should the documentation live
Project management/issue tracking
System Relationships

Drupal and eXist: query and response. JSON? XML?
Drupal and Hydra: ingestion and preservation. TEI Data
Team Responsibilities (Scott and Julia are represented at all levels)

Drupal
Accounts
Ben, Linda, Eli
Upload/Configure/Projects
Eli, Will, Ben, Linda, Eli
Search/Browse
Eli, Ben, Linda, Eli
Reading Interface
Eli, Syd, Ben, Linda, Eli
System Admin
Karl
Drupal --> Hydra, TEI Data transfer (put, push, or get?)
Ashley, Will, Syd, Sarah
Hydra
Sarah, Will, David
System Admin
David
Fedora
Sarah, Will, David
System Admin
David
Hydra <--> eXist (query and response)
Ashley, Syd, Julia
eXist
Ashley, Syd
System Admin
Karl
Wild Apricot --> Drupal
Eliot, Linda
Wild Apricot
John Unsworth
Quality Assurance
TBD
Documentation
User Facing: Need public facing rationals for our users (What kinds of TEI can I upload and why?)
Ben, with guidance from Ben and Scott
Development and General Project Documentation
Dependancies need to be well documented in GitHub. Need documentation for architectural pieces. i.e., How does Drupal do X?
Technical documentation. Linda will take control of this, Ashley will co-own the responsibility
Where to look? Consult with Will and David on how best to document the development code.
Feature Requests/Issue Tracking
TAPAS Generated
Git
As assigned (someone will need to handle unassigned issues)
User Generated
Triage
Ben (will get info from users, discussion lists, etc), Julia, ?
Decision
Whole team
Questions

Linda: How do we communicate about how the dev server is being used? When is it save/unsafe to use? Could be solved by server allocation, and redefining of current environments (test, development, and production)
Linda: Is there a QA procedure to go from test to live?
Syd: No, except for common sense. We put out the word: Test this please.
Julia: Some testing does get done via beta testers. Now is a time to recruit beta testers for the kinds of QA we want (design issues, weird data). Commission a small group to integrate the plan.
Patrick: may integrate selenium (http://www.seleniumhq.org/): Run a test to make sure queries don't fail. Nagios is running to ping all our services, we should make sure Nagios is running for TAPAS.
Julia: Need to break this out as a work stream? Need a checklist of things that need to be tested. Brainstorm in another session, then select a point person to organize the future testing.
Syd: Develop a work suite of files, some that fail and some that succeed. Test the ability to create and delete users
Sarah: What is Wild Apricot
Julia: Wild Apricot is storefront that TEI consortium uses to manage who has access via TEI membership (managed by John Unsworth; Eliot is most knowledgeable about how the API works to connect WA and Drupal)
Linda: How do we prioritize feature requests?
Julia: Have a periodic meeting at intervals to look at current requests and prioritize them, so that Ben can communicate back to users what we plan to do. Create a core triage group.
Patrick: For the advisory board? May meet too infrequently for practical purposes.
Hydra Head will be packaged and made available

Future Meetings:

Brain dumps on interfaces
Bug/Feature Tracking (Set up the GitHub issues list to incorporate the details of this communication map. Milestones? Goals of the grant?)
January 15, 2015
Rough notes from Jim; Sarah will edit / revise / expand.

Review / Discussion of roles

Julia: Co-Director / XML, Searching, TEI component (works w/ Ashley and Syd) on Syd: TEI Specialist; what happens to TEI documents in TAPAS: what do we validate, how do we show them (reading interface) Patrick: signed to TAPAS grant; broker institutional agreements / expertise in repository architecture Sarah: added to grant: working on XSLT stylesheet to transfer metadata to MODS for repository Eli: user interface Ashley: XML applications developer; cool things we can do with TEI documents; upgrading eXist Ben: Project Manager; filter from front-end user to development team; better documenting various tasks and workflows; establishing better lines of communication (thing Ben mentioned) Linda: new DRUPAL developer: digging through documentation left by old DRUPAL developer; working on data dictionary Will: working on connection between DRUPAL and Hydra; built dev environment / virtual machine stuff

Scott Hamlin: project Co-Director at Wheaton (weekly phone calls between Ben, Julia, and Scott); TAPAS originator Elliot Scott: original DRUPAL developer; in orbit to answer questions Nathan Doyle: independent contractor doing DRUPAL work (remote / emergency basis); Nathan and Elliot have documented security updates Karl: systems-level issue David Cliff: out of the office / on grant

To-be-hired: data visualization person

Overview of areas to discuss this semester 1.distinct strands of work / workflow 2.systems: where things live, how they get updated; data management systems 3.communication mechanisms: where documentation has accumulated 4.project management issue: issue tracking systems

map of relations

Drupal: built first (content management system) in first grant: provides user environment where people can upload TEI data; create projects (organization-level entities); create collections within projects; manage data and configure how it will be displayed in reader interface a simple environment for uploading, managing, and publishing TEI data

long-term curation of TEI data: use of Hydra, Fedora, eXist

in the future: we’d like to stop using Drupal: not the interface that we’d like to use re-building TAPAS using Hydra and then allowing Drupal to wither: not in the scope of this grant and ambitious, so it may be the next grant; for current grant, thinking about opportunities where work might help facilitate transition without compromising current work

budgetary implications: coherent, single-page recommendation for architecture need for a third full server or whether it can be done through a desktop application come back in two weeks (end of January) to look at implications (instead of large VM, two small VMs); tied to need for “skunk works”

Sarah's Notes:

General TAPAS Review Topics: What are the groups and roles for the TAPAS group? Systems and where things live? How do they get updated? Communication mechanisms Project management/issue tracking

Migrating Drupal to Hydra is outside the scope of this grant.

Questions:

Drupal: Is there a deployment plan? Production and Development Drupal sites are not in sync. Proposed: need a third for testing work (sandbox)? Need a recommendation for new architecture (move to one large and two small VMs, rather than two large VMs and one small. (Patrick and Julia will need to consider the budget implications.)
Where do VMs fit into the workflow? A vagrant instance runs Drupal, hydra, and eXist. This is the Plattr GitHub repository.
TAPAS project broad categories:

Fedora/Hydra
TEI
XQuery/XML DB/eXist
User interface
Accounts/User Data/People management?
Visualizations
What is being transferred between systems (represented in the graph)? Data, metadata, -ographies, etc. Who is working on these things? Who needs to be consulted?

Fedora/Hydra --> Drupal: Drupal upload process to Hydra; bilateral connection; where to generate the TFC and how to tackle that? Drupal --> eXist: XQuery; data returned? is the relationship between files the same in Drupal and eXist?

Future Discussions:

Deployment architecture and implementing Drupal Features (invite Ernesto). Eli will take a look at how difficult it would be to implement Features (https://www.drupal.org/project/features) in Drupal.
TAPAS Friendly Copy (TFC: TEI amended with TAPAS specific data.)
When is the TFC created? When TEI data is added to Drupal, but the TFC generation might be better done through Fedora. Where the TFC is generated will affect what eXist communicates with.
The original is kept, in addition to the TFC.
eXist
How to mediate permissions: should go through Hydra, or should talk directly to eXist? eXist will return XML to Drupal.
How things are "unpacked"?
How will data be manipulated or visualized? Will eXist have to return XML and JSON? Should Drupal be doing the JSON transformation?
eXist needs its own GitHub repository? Figure out where eXist should live in the Library GitHub world.
White Board - January 15, 2015

January 8, 2015
Ashely:

Exist doesn't handle file metadata well Private and public information will be handled (unique identifiers, collection, user created) will be handled by the TPC. Exist will get the TPC, not the original file. TPC will need to be updated to include all of that information. Create the TFC as part of the core file creation, not as part of the upload process (it's currently step number two). Is the metadata from step two actually written to the TPC?

Moving files between projects. Investigate how "organic groups" handles relationships ("organic groups" is a Drupal module).

Security updates? Has Nathan been charged with this?

Need to have an a way to communicate with all TAPAS users (Drupal interface? Listserv)

Documentation - Ben and team currently use a Google site: https://docs.google.com/document/d/1xC3pOWedlL3UnwtFnUakATNdwVSexPqb5dYDI7Xp-fA/edit?usp=sharing

Linda Moss

Tasks:

Revisions/editing for TEI
Can only view the old version of the file, get the file. Can't revert the file. Just tracking all the copies that have existed. Titles are updated to include the revision date (also, "revision" is spelled wrong).
Field data needs to gets written to the TFC
Code audit of Drupal modules
"There may be a large part of the code base that doesn't do anything."
Cosmetic tweaks
Reimplement everything Elliot did to core
Orientation:

Sketch out all the TAPAS components (Syd is necessary for this)
Coordinate with Nathan and Elliot about their work? Including updating Drupal versions (7.3.1 or 7.3.2?)
Access to TAPAS/TEI membership
Get a dev environment
Create accounts for her/get admin status
Julia needs to meet with Unsworth to talk about the functional relationship between TAPAS and TEI membership (Ben)
SSH access - Karl
GitHub permissions (Will - add Ben, too)
Mailing lists (Karl, Syd)
Developer list for error reports?
TAPAS orientation for everyone (GitHub, wiki, etc)
December 18, 2014
Julia reviewed the goals of the TAPAS grant: 1. Build and XML aware repository 2. Allow users to interact with XML data as XML data, not just a blob of data

Ashley is currently working with the XML data base (getting it up and running and getting it to recognize public and private items). Ashley's next steps:

Count how many elements appear in the corpus
Make sure Hydra can communicate with eXist and tell it what it wants
Will is currently working on getting support files to make it into Hydra (just images, for now). Will's next steps:

Look at -ographies
Set up the newly established verbs in Cerberus Core
We all agreed that there needs to be coordination between TAPAS team members working on/with Drupal. Julia will email the Drupal-oriented team members and Will will follow up with instructions/best practices/foundational information about working with Drupal.

*December 11, 2014*
New RELS-EXT relationships for TAPAS:

all have drs:isPartOf
Collections
Text
TEI
drs:isTranscriptionFor vs drs:isTranscriptionOf
JPG
drs:isImageFor
drs:isPageImageFor
drs:hasSequenceFor (for sequencing)
Xgraphies (separate out the graphics to anticipate for other projects to leverage the specific ography information)
drs:isXographyFor
drs:isPersonographyFor
drs:isPlaceographyFor
drs:isOrgographyFor
drs:isBiblographyFor
drs:isOtherographyFor
ODD
drs:isODDfileFor
XML
White Board - December 11, 2014

December 4, 2014
White Board - December 4, 2014
