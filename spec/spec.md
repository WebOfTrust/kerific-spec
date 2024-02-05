## Consensus Feature for Kerific

[ [Reiktewijdte] discrepanties met github role / repo] "Form" heeft reiktewijdte als intentie.

### What is Kerific?
Kerific is a browser plugin or extension that currently (as of January 2024) is compatible only with Chrome and Brave browsers. It identifies and matches terms within any web-text that is parsable by Kerific, offering buttons that link to various glossaries and definitions in the Self-Sovereign Identity (SSI) field.

### Relationship with KERISSE
All glossaries that KERISSE is permitted to scrape are amalgamated into its Unified Glossary. This is based on a large JSON file, which Kerific utilizes to align words in any text and provide the combined glossaries.

### Extension with Consensus Feature
This specification covers the extension of Kerific, including the use cases and the Create, Read, Update, (Delete) - CRU(D) - of terms.

#### What is the Consensus Feature?
The Consensus feature allows Kerific users to flag terms and definitions for adoption or to copy for their own managed use. Depending on the user's role, the Consensus feature leads to the perpetuation (the distribution and display) of their choices among their peers and to the external world.

This resolves three issues simultaneously:
- The world is as you see it; you cannot blindly trust another's descriptions.
- You often think you're talking about the same thing, but that's not always the case.
- Creating and maintaining one's own concepts and terminology requires a lot of energy.

**"I don't see the problem"**  
That's possible. You'll naturally feel the problem when you and a group have a groundbreaking goal in mind in a new field of work and you want to communicate with the outside world.

#### Who is the Consensus Feature of Kerific for?
Kerific is intended for a very broad group of users: those interested in explanatory texts about SSI-related content on the internet.
However, the Consensus feature is specifically aimed at creators and maintainers of terminologies for specific groups. They are most probably authors of technical documents that need to reference glossaries/glossary entries. They also belong to the general Kerific user group.

#### How are the following roles supported?
- Main authors of the objective and concepts behind the group - YES
- Authors of glossary terms – YES
- Users of glossary terms – YES
- Curators of glossaries (manage changes, toolsets, etc.) - NO
- Glossary Tech developers - NO
- Instructors and educators on behalf of ToIP - NO

#### What advantage/goal does the Consensus feature have?
- Integrating scopes into other scopes
- Saving time
- Removing duplicity
- Building group consensus

### Origin of the Consensus Tool in Three Sequential Steps
- 2022: KERISSE hosts the destination of the Web of Trust glossary.
- 2023: KERISSE creates the unified glossary from all known structured meaningful SSI glossaries.
- 2024: Kerific visualizes the unified glossary, displaying the collections of definitions gathered by various parties at the push of a button.

With Kerific showcasing the unified glossary and all scopes becoming transparent within the context of a random document, two effects take place:
A. Every user can read the definitions within the scopes of various groups and approaches.
B. A user in a certain role can go through their documents online and select definitions for their own glossary (which is in the making).

_NB. The assumption that you can just copy glossary definitions from another or from the overarching group for your own purpose and group is a misconception that should be dispelled as soon as possible._

### Terms within the Context of This Design
'Kerific' as a concept and scope falls within the framework of eSSIF-Lab and TEv2. On top of that, we define:
- 'Organization' is at the level of Trust-over-IP.
- 'Group' is a working group or any other subgroup you can think of within TrustoverIP, but it can also refer to a subdivision elsewhere.
- `part_gloss` is the glossary of a group.

#### What is a Creator?
- Someone who defines a term from scratch for the first time, and the term may already exist as well as the definition (in the latter case, the creator is not aware and has not followed the correct procedure).
- Someone who copies and changes or supplements the definition of a term.

#### What is adoption?
The act of starting to use a particular plan, method, way of speaking etc (from: Longman dictionary). 
Our scope narrows this down: it's all about descriptions and definitions in text. Criterium: Is this the case? Yes -> it might be adoption for us. 

Our scope narrows the term adoption further down: we are in the digital world on the internet and we're handling concepts & terminologies for SSI field.

Criterium: Is this the case? Yes -> it might be adoption for us. 

> Example of referencing to a terms definition in the real world, which is not adoption to us: 
quoting a definition from a physical dictionary.

##### What is an Adopter?
Someone who labels a term *as is* as the definition of a term from their role within their group and scope.

The next criterium for *adoption* is: are there "one of more" adopters for an adoptee. Yes -> adoption might be the case.

##### What is the Adoptee?
In our scope it's a concept or a term of a certain origin, used by some other external scope or over-arching scope.

The next criterium for whether *adoption* in our scope is at hand: Is/are there one or more other scopes explicitly and knowingly referencing a definition of some other origin *as is* created/updated at some point in time in the past? If yes -> there is adoption.

Another criterium that *excludes* adoption: Have you copied the source of a concept or terminology? If yes, it's not adoption. Adoption leaves the text at a certain point in time created/updated intact *as is* and explicitly refers/links to it.

The last criterium that makes adoption: Do we know who did it? If yes, it's adoption. 

There may be various reasons for adopting a concept or a term depending on the role you have and the task you perform:
- create a glossary efficiently
- curate a terminology
- build consensus
- adhere to governance rules

#### The source of terminology
The source of terminology is the unique place where the singular source of a group's terminology stands. It is edited with a source edit tool, which saves the user's edits and commits with git, thereby capturing the order and timing.

#### The destination of terminology
The destination of terminology is the appearance of a terminology or the full-featured glossary. The destination is preferably used to link from adopting and referring content. The destination preferably has a one-to-one link offered to its own source of a term.

_'Scope' is a simpler word for mental model._

_'Anchor registry' is a table where we store the permanent anchor-glossary combinations because the terms were once adopted. If the adoption disappears, it's fine, but if the anchor disappears, it can lead to broken links elsewhere. Hence, a registry._

### Why this Consensus Feature?
- Integration (creating consensus over similarities and differences of understanding) between dictionaries where possible.
- Work-saving.
- Better understanding each other.

### Current Situation of Kerific
The bookmark operates independently from the Extension. You can drag it into your bar from the web page, which is located in /test.

#### Example Google Doc of a project without a glossary (by that time)
[Link to Google Doc](https://docs.google.com/document/d/1zrBKAMGgWcXnj4fzOOdyBBZbkRbjpE3k/edit)

### Governance implications
#### Challenge:
When adopting the term, the anchor of the destination must be permanent.

#### Solution:
Then Kerific must be reprogrammed because we choose our own anchor ID at that moment.

Each glossary we scrape has its own import routine. What we often do is grab the text and flatten it, removing spaces, toLowerCase, etc.

Imagine you create an anchor from the term itself (as we often do) but then replace spaces with dashes, and single dashes with double dashes. And so a few fixed rules. Then you have a unique anchor for each term.

Generating a random ID for certainty, or adding a Unix timestamp, in case definitions overlap or lead to broken links.

If we want to have permanent destination anchors, then we must come up with something else. We then have to make a lookup table, an anchor registry.

#### Example use case
The Actor definition of ToIP as my choice for adoption in my glossary WannaHave.

Suppose: At time X, date D -> then there is a version of gloss ToIP V that ends up in the unified gloss U.

In this example, we must link a generated anchor from that moment to a term, and because you want it to be permanent from WannaHave, we must come up with something else.

##### Option 1: Unix timestamp
So we can use a Unix timestamp, I like that. Then you can even see later when the anchor was made permanent.

##### Option 2: Git
Why don't we use GIT to record the order in the creation, adoption, update of terms? We don't need a timestamp per se; we need the order. Git commits seem to lend themselves to that?!

We now have a unified glossary in JSON form. We can ensure that in the code no anchor is added if there is already an anchor.

For the C of CRU, we are then ready: only add an anchor if it does not exist.

#### C of CRU
Once a term is created/claimed, it is in the unified glossary (combined glossary) for the respective `part_gloss`.

- Term-part_gloss combination is unique for now
- Term-organization is not. Toip will soon have many part_glosses.

Study the JSON file of the unified glossary:
[Link to JSON file](https://github.com/WebOfTrust/WOT-terms/blob/main/static/json/external-glosseries/glossaries-combined/all-glossaries.json)

So actor-toip is the overarching glossary of ToIP.

I have chosen in the code to use one of the anchors as the definitive anchor.

### The Process of Creating Terminologies
We describe the governance, the process to arrive at the creation and management of terminology of a group in conjunction with overarching collaborations.

Toip as an org has many groups, each with its own `part_gloss`.

In addition, Toip has an overarching (part)glossary.

Each group can create exactly the same term (by writing or copying) or at any time decide to adopt and no longer update themselves.

#### MENTAL MODELS of eSSIF-lab and Rieks Joosten

##### Starting Points
- You have your own reality as a group,
- You have a role within the group,
- You have your own reality as an individual.

#### Use Cases of the Consensus Feature Kerific
Every group can create exactly the same term (by writing or copying) or at any time decide to adopt and no longer update themselves.

We must describe the CRUD of this game.

Every term-group is a unique anchor because you never Delete a term, only Create or Update or adopt/read -> Read.

My scope as a group overlaps with yours for all the terms I adopt from you and you from me.

As soon as I take control of a term (copy or create new) and possibly change it, I indicate that I think our scopes diverge on at least that exact term.

Whether now one, two, or three groups claim a term, the term is unique, and if you create an anchor from it, it is also unique if you replace a space with a dash, etc. But then we have to agree that uppercase and lowercase are seen as the same.

As soon as I take control of a term (copy or create new) and possibly change it, I indicate that I think our scopes diverge on at least that exact term.

The term changes? Then a new anchor arises, that is then the consequence.

Only if I adopt, does that not happen.

The term gets a unique anchor; but if two groups adopt the term, can they choose their own anchor?

It seems better to use the anchor to the anchor of the unified-glossary and to the destination of the creator of the glossary.

The worst thing that can happen is the following:
- A group does delete (against the agreements) its gloss -> one of the adopting groups copies an old version and the rest adjusts the links.
- A term is removed (also against the agreements), then the link still always comes out at the group's gloss but remains at the top.

If you adopt a term and the source group deletes it, then you are temporarily in trouble.

#### Solution: 
You take an older version of term-group and manage it yourself.

Then the group that adopted thinks, shoot, we had adopted it but I have no idea what it was ->
Therefore, something semantically meaningful must be attached to the permanent link to the adopted:
Term-group-version?

Term-group-version also gives insight into IP history, who created, who copied, who adopted.

Therefore, we wonder if we are not close to option 2, GIT.

#### Use Cases Effect
And you see then that a group has thought well about terminology, even if they have only written 5 defs themselves. But because they have adopted 236 and you see exactly from whom and not, you know they are far in their thinking.

I get the feeling of a 'Spotify playlist' that is subtly compiled.

I indeed also want to take over the adoption+management list of group G! And build on that.

However, it should not be too easy to just declare a whole glossary "applicable" to a group. That is governance, we cannot prevent it, but discourage it and promote group decision-making (thumbs up/down) on term defs per group.

### Prolongation
We want to express the adoption of a term as a fact in the unified glossary through a registry. How else can you later see that the ToIP definition has been adopted a lot and that of NIST, for example, has not. This feature is like "fork" in GitHub: you can see how many other users maintain an active/recent fork of a repo.

The main authors of the concept of a group have made a collection {{ [adopted], [copied], [new] }} either individually or not.

This collection of choices must be documented in the unified glossary. The reason for this is:
- Followers must be able to see what the leaders want to convey in terms of concept and terminology.
- Adopted terms are heavily loaded (must get a permanent anchor).
- Copied terms are burdened with bread-crumb reference: when from whom what in which version was copied to the own terminology.

The term gets a unique anchor. If there are two groups that keep a term almost identical themselves and therefore there are two anchors in the registry, they and others may choose their own anchor for references. Here, this design of the Consensus feature cannot take this into account. It falls outside our scope. Kerific only shows what the status of consensus is, it does not mediate, and it does not correct; that is people's work.

#### Recording an anchor in JSON
We then have a unique ID and it is recorded in JSON and belongs to that JSON entry from that moment on.

##### Option 1 Timestamp
If we generate an anchor based on a Unix timestamp, plus a random number, we have something unique, we record that, and we already have that.

##### Option 2 Git
Or a GIT commit number?
