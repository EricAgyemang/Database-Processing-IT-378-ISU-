# Database-Processing-IT-378-ISU-
Advanced knowledge in database concepts, emphasis on relational databases, SQL, data modeling, database design, DBMS functions, database application programming, current trends, design project.

# SECTION 1
# The Database System Environment
  Database system consists of five main parts:
  * Hardware
  * Software
      1. Operating system software
      2. DBMS software
      3. Application programs and utility software
  * People
  * Procedures (rules governing the design and use of a DB system)
  * Data

# DBMS Functions
  DBMS guarantees data integrity and consistency
  * Data dictionary management
   - defines data elements and their relationships
  * Data storage management
   - stores data and data entry forms, report definitions, etc.
  * Data transformation and presentation
   - 14/01/2009 or 01/14/2009?
  * Security management
   - enforces user security and data privacy within database
  * Multiuser access control (i.e., concurrency)
   - Backup and recovery management

# SECTION 2
# Relational Data Models
 * Entity - anything about which data are to be collected and stored (e.g. person, thing, event, place)
 * Attribute - a characteristic of an entity
 * Relationship - describes an association among entities
   - One-to-many (1:M) relationship 
   - Many-to-many (M:N or M:M) relationship
   - One-to-one (1:1) relationship
 * Constraint - a restriction placed on the data to ensure data integrity

# Business Rules
 * How do you identify entities, attributes, relationships and constraints?
 * Business Rule
   - Brief, precise, and unambiguous descriptions of a policy, procedure, or principle in an organization
       E.g. classes with < 5 students will be canceled
       E.g. an order has to be > $100 to get free shipping
   - Apply to any organization (not just business orgs)
   
# Translating Business Rules into Data Model Components
* Generally, nouns translate into entities
* Verbs translate into relationships among entities
* Relationships are bidirectional
* Two questions to identify the relationship type:
   - How many instances of B are related to one instance of A?
   - How many instances of A are related to one instance of B?

# Naming Conventions
  * Naming occurs during translation of business rules to data model components
    - Names should make the object unique and distinguishable from other objects
    - Names should be descriptive of objects in the environment and be familiar to users
  * Proper naming:
    - Facilitates communication between parties
    - Promotes self-documentation.
    
# Data Models
 * Each new data model improved on the previous ones.
   - Network Models replaced Hierarchical Models because it better represent M:N relationships.
   - Relational Models thrived with its data independence, simple data representation, easy-to-use query language.
   - OO have gained a substantial foothold, but cannot yet dislodge Relational Models.
   
# A Logical View of Data
  * Relational model 
    - Enables programmer to view data logically rather than physically
  * Table 
    - Has advantages of data-program independence.
    - Resembles a file from conceptual point of view.
    
 # Tables and Their Characteristics
  * Table:  Two-dimensional structure composed of rows and columns
    - Codd used table and relation interchangeably
  * However, a relation must also satisfy the following:
    - Every row (record) must be unique
    - Every attribute value must be atomic (not multivalued)
    - The order of rows and columns must be irrelevant
    - Attributes (columns) must have unique names.

# Keys
A key consists of one or more attributes that determine other attributes
  * Key’s role is based on determination
  * If you know the value of attribute A, you can look up (determine) the value of attribute B.
  *  Primary key (PK)
     - An attribute (or a combination of attributes) that uniquely identifies a row 
  * Composite key
    - Composed of more than one attribute
  * Key attribute
    - Any attribute that is part of a key
 
  * Foreign key (FK) 
    - An attribute whose values match primary key values in the related table
  * Referential integrity 
    - FK contains a value that refers to an existing row in another relation

# SECTION 3
# The Entity Relationship (ER) Model
  * ER model forms the basis of an ER Diagram
  * ERD represents conceptual database as viewed by end user
  * ERD depicts database’s main components:
   - Entities
   - Attributes
   - Relationships

# Relationships
  * Association between entities
  * Participants are entities that participate in a relationship
  * Relationships between entities always operate in both directions
   - Relationship is difficult to classify if only one side of the relationship is known.

# Connectivity and Cardinality
 * Connectivity 
   - Describes the relationship classification (1:1, 1:M, M:N)
* Cardinality 
   - Expresses min and max number of entity occurrences associated with one occurrence of related entity
* Established by very concise statements known as business rules.

# Relationship Strength
 * Weak (non-identifying) relationships
  - Exists if PK of related entity does not contain PK component of parent entity
 * Strong (Identifying) Relationships
  - Exists when PK of related entity contains PK component of parent entity

# Weak vs. Strong Entities
 * Strong entity (or regular entity)
  - Can exist apart from one or more related entities
 * Weak entity meets two conditions
  - Existence-dependent
    * Cannot exist w/o entity with which it has a relationship
  - Has PK that is partially or totally derived from parent entity in relationship
 * DB designer usually determines whether an entity can be described as weak based on business rules.

# Relationship Participation.
 * Optional participation
  - One entity occurrence does not require corresponding entity occurrence in particular relationship
 * Mandatory participation
   - One entity occurrence requires corresponding entity occurrence in particular relationship.

# Relationship Degree.
 * Indicates number of entities or participants associated with a relationship
 * Unary relationship
   - Association is within single entity; recursive 
* Binary relationship 
   - Two entities are associated
* Ternary relationship 
 - Three entities are associated

# Recursive Relationships.
 * Relationship can exist between occurrences of the same entity set
 * Naturally found within unary relationship.

# Composite Entities.
 * Also known as associative, or bridge entities 
 * Used to implement M:N relationships
 * Composed of PKs of each of the entities to be connected
 * An alternative to adding attributes to relationships
  - In Chen’s original ERM, relationships did not have attributes.

# Developing an ER Diagram.
 * Database design is iterative, rather than linear or sequential process
 * Building an ERD usually involves the following:
   - Create detailed description of organization’s operations
   - Identify business rules based on these descriptions
   - Identify entities and relationships from business rules
   - Develop initial ERD
   - Identify attributes and PKs that describe entities
   -  Revise and review ERD.

# Database Design Challenges.
 * Conflicting goals: design standards, processing speed, information requirements
 * DB design must conform to design standards
  - Must minimize redundancies and anomalies
 * High processing speed is often a priority in DB design
  - By minimizing the number of complexity of relationships
 * Quest for timely information might be focus of DB design
  - Have to sacrifice “clean” designs and speed to ensure max info generation 

# ERD notations
  1.	Entity names should be in ALL CAPS and in singular form (e.g., CAR rather than CARS)
  2.	Relationship names must be one verb.  (Use underscores if it is more than one word.)  Relationship names must also be in singular, third person plural form (e.g., “sends”) though 
      it is also okay to use the passive tense (e.g., “sent”).  However, “sends/receives” or “sent/received” would be illegal.
  4.	Depending on the strength of the relationship, the line needs to be either solid or dotted.



# What is the difference between Relationships with Attributes and Composite/Bridge Entities?
  * They are closely related.  In fact, the former can be viewed as an intermediate result before reaching the latter, which is the final outcome.  
  * In early phases of DB design, relationships with attributes are acceptable.  However, they must be converted/decomposed into composite/bridge entities before the design becomes    
    implementable.  So, the use of bridge entities is preferred, but unless otherwise noted, relationships with attributes can still be used.

# SECTION 4
# Entity Supertypes and Subtypes
 * Entity supertype 
   - Generic entity type that is related to one or more entity subtypes
   - Contains common characteristics
  * Entity subtypes 
   - Contains unique characteristics of each subtype
   -
# Specialization Hierarchy
 * Entity supertypes/subtypes are organized in a specialization hierarchy
    - It depicts arrangement of higher-level supertypes (parent entities) and lower-level subtypes (child entities)
 * Subtype can exist only within context of supertype 
 * Every subtype can have only one supertype to which it is directly related
 * Can have many levels of supertype/subtype relationships
 * Provides the means to:
   - Support attribute inheritance
   - Define special supertype attribute known as subtype discriminator
   - Define disjoint/overlapping constraints and complete/partial constraints
   
# Inheritance
 * Enables entity subtype to inherit attributes and relationships of supertype
 * All entity subtypes inherit their PK attribute from their supertype
 * At implementation level, supertype and its subtype(s) maintain a 1:1 relationship
 
# Subtype Discriminator.
 * The attribute in supertype entity that determines to which entity subtype each supertype occurrence is related
 * The default comparison condition for subtype discriminator attribute is equality comparison.

# Disjoint and Overlapping Constraints.
 * Disjoint subtypes
   - Also known as non-overlapping subtypes
   - Subtypes that contain unique subset of supertype entity set
  * Overlapping subtypes
   - Subtypes that contain nonunique subsets of supertype entity set.
   
# Completeness Constraint.
 * Specifies whether each entity supertype occurrence must be member of at least one subtype
 * Can be partial or total 
   - Partial completeness: not every supertype occurrence is a member of a subtype
   - Total completeness: every supertype occurrence must be a member of a subtype
   
# Specialization and Generalization.
 * Specialization
   - Top-down process of identifying entity subtypes from entity supertype
   - Based on grouping unique characteristics and relationships of the subtypes
 * Generalization
   - Bottom-up process of identifying generic entity supertype from lower-level entity subtypes
   - Based on grouping common characteristics and relationships of the subtypes.

# Design Considerations: - Selecting Primary Keys.
 * PK is the most important characteristic of an entity
   - Single attribute or some combination of attributes
 * The PK’s function is to guarantee entity integrity
 * PK and FK work together to implement relationships
 * Properly selecting PK has direct bearing on efficiency and effectiveness.
 
# Natural Keys and Primary Keys.
 * Natural key is a real-world identifier used to uniquely identify real-world objects
   - Familiar to end users and forms part of their day-to-day business vocabulary
 * Generally, data modeler uses natural identifier as PK of entity being modeled
 * May instead use a surrogate key

# When to Use Composite Primary Keys
 * Composite primary keys useful in two cases:
  - As identifiers of composite entities
    * In which each PK combination is allowed once in M:N relationship
  - As identifiers of weak entities
    * In which weak entity has a strong identifying relationship with the parent entity
 * Automatically provides benefit of ensuring that there cannot be duplicate values.
 
# When To Use Surrogate Primary Keys.
* Especially helpful when there is:
  - No natural key
  - Selected candidate key has embedded semantic contents
  - Selected candidate key is too long or cumbersome

# When to use supertype/subtype entities?
To justify the use of supertype/subtype entities, one of the following two conditions must be met:
 * At least one of the intended subtypes has a unique attribute, OR
 * At least one of the intended subtypes has a unique relationship with another entity, that is an entity outside the supertype/subtype hierarchy.
If neither of the above condition is met, the use of supertype/subtype will not be justified.

# The Completeness Constraint 
Depending on the textbooks you use, some prefer terms like totally vs. partially complete, and others prefer complete vs. incomplete.  The idea is the same.  ER-Assistant is in the latter camp with a "complete" box that also means "totally complete."  If you leave the box unchecked, it would mean "incomplete" or "partially complete."

# Should the inherited PKs in subtype entities be shown in the ERD?
  The subtype entities inherit their PKs from the supertype. And as a result, many would just omit the PKs from the subtype entity boxes since their PKs are implied.  However, some  designers prefer to make the inherited PK explicit, and sometimes name them a little differently to avoid confusion –If the supertype PK is StudentID, the subtype PKs may be named UG_StudentID and G_StudentID.  Again, these are still inherited from StudentID, but with a clearer distinction.  The very last slide of Module 5 has another example for that.
  

# SECTION 5
# Key Fields
 * Keys are special fields that serve two main purposes:
   - Primary keys are unique identifiers of the relation in question. Examples include employee numbers, SSN, etc. 
   - Foreign keys are identifiers that enable a dependent relation (on the many side of a relationship) to refer to its parent relation (on the one side of the relationship)
 * Keys can be simple (a single field) or composite (more than one field)
 * Keys usually are used as indexes to speed up the response to user queries


# Integrity Constraints
 * Domain Constraints
   - Allowable values for an attribute (e.g. integer 3 digits)
 * Entity Integrity
  - No PK attribute may be null. All PK fields MUST have data
 * Referential Integrity Constraint
  - Any FK value (M side) must match a PK value in the relation of the 1 side. (Or the FK can be null).
  
 
 # Transforming EER Diagrams into Relations.
 - Mapping Regular Entities to Relations 
  * Simple attributes: E-R attributes map directly onto the relation
  * Composite attributes: Use only their simple, component attributes 
  * Multivalued Attribute: Becomes a separate relation with an FK taken from the superior entity.
  
- Mapping Weak Entities
  * Becomes a separate relation with an FK taken from the strong entity
  * PK composed of:
  * Partial identifier of weak entity
  * PK of identifying relation (strong entity)

- Mapping Binary Relationships
  * 1:M – PK on the one side becomes an FK on the many side
  * M:N – Create a new relation with the PKs of the two entities as its PK
  * 1:1 – PK on the mandatory side becomes an FK on the optional side.
 
- Mapping Associative Entities
  * Identifier Not Assigned 
    • Default PK for the association relation is composed of the PKs of the two entities (as in M:N relationship)
  * Identifier Assigned 
   * It is natural and familiar to end-users
   * Default identifier may not be unique.
   
- Mapping Unary Relationships
  * 1:M – Recursive FK in the same relation
  * M:N – Two relations:
  * One for the entity type
  * One for an associative relation in which the PK has two attributes, both taken from the PK of the entity.
 
- Mapping Ternary (and n-ary) Relationships
  * One relation for each entity and one for the associative entity
  * Associative entity has FKs to each entity in the relationship

- Mapping Supertype/Subtype Relationships
  * One relation for supertype and for each subtype
  * Supertype attributes go into supertype relation
  * Subtype attributes go into each subtype
  * Subtype relations inherit the supertype’s PK 
  * 1:1 relationship established between supertype and each subtype, with supertype as primary table

# ERD Conversion Rules
Basic Conversion Rules:
  1. Each entity type becomes a table.
  2. Each attribute becomes a column.
  3. Each 1-M relationship becomes an FK in the M table (the entity type near the crow’s foot symbol).
  4. Each M-N relationship becomes a bridge table with a combined PK (or a new PK if appropriate).
  5. Each identifying relationship adds a column to a PK.
 
Specialized Conversion Rules:
  6. Generalization Hierarchy:
    •	Each subtype table contains specific columns plus the primary key of its parent table.
    •	For each subtype table, foreign key constraints must reference the parent table.
  7. 1-1 Relationship Rule:
    •	When any one cardinality is optional one:  PK on the mandatory side becomes an FK on the optional side
    •	When each cardinality is mandatory one: PK on any mandatory side becomes an FK on the other side.
    
    -------------------------------------------
    *Note:*
       •	Self-referencing relationships follow the basic 1-M or M-N rules.
       •	Identification dependency (weak entity) follows basic conversion rules for identifying relationships, 1-M and/or M-N relationships.


# SECTION 6
# Database Normalization
 * Primarily a tool to validate and improve a logical design so that it satisfies certain constraints that avoid unnecessary data duplication
 * The process of decomposing relations with anomalies to produce smaller, well-structured relations

# Well-Structured Relations.
 * A relation that contains minimal data redundancy and allows users to insert, delete, and update rows without causing data inconsistencies
 * Goal is to avoid anomalies
   - Insertion Anomaly–adding new rows forces user to create duplicate data
   - Deletion Anomaly–deleting rows may cause a loss of data that would be needed for other future rows
   - Modification Anomaly–changing data in a row forces changes to other rows because of duplication.
    
     --------------------------------------------------------------
     Note:
          • General rule of thumb: A table should not pertain to more than one entity type.
     --------------------------------------------------------------

# Functional Dependencies and Keys.
 * Functional Dependency: The value of one attribute (the determinant) determines the value of another attribute
 * Candidate Key:
  - A unique identifier. One of the candidate keys will become the primary key
  - E.g. perhaps there is both credit card number and SS# in a table… then both are candidate keys
  - Each non-key attribute is functionally dependent on every candidate key.

# First Normal Form.
 * No multivalued attributes
  - Every attribute value is atomic
 * All relations are in 1st Normal Form.

# Second Normal Form (2NF)
 * 1NF PLUS every non-key attribute is fully functionally dependent on the ENTIRE primary key
 * Every non-key attribute must be defined by the entire key, not by only part of the key
 * No partial functional dependencies.
 
# Convert to 2NF.
 * Create a new relation for each PK attribute that is a determinant in a partial dependency.  That attribute becomes the PK of the new relation.
 * Move the non-key attributes dependent on the new PK to the new relation.

# Third Normal Form (3NF)
 * 2NF PLUS no transitive dependencies (functional dependencies on non-PK attributes)
 * Called transitive, because the PK is a determinant for another attribute, which in turn is a determinant for a third

# Convert to 3NF.
 * Non-key determinant with transitive dependencies goes into a new relation
 * It becomes PK in the new relation and stays as FK in the old relation 

# Normalization and Database Design.
 * Normalization should be part of design process
 * Proposed entities need to meet required normal form before table structures are created
 * You may be asked to redesign/modify existing DBs
 * Existing DBs may have been improperly designed or burdened with anomalies, or improperly modified over time

# Denormalization.
 * Creation of normalized relations is an important design goal
 * Processing requirements should also be a goal
   - Number of DB tables expands in the normalization process
   - Joining more tables takes additional I/O operations and processing logic, thereby reducing system speed
   - Conflicts between design and performance goals are often resolved through compromises that include denormalization
 * Under some circumstances, unnormalized tables are better choice 
 * Use denormalization cautiously.


# SUMMARY OF DATABASE SYSTEMS
  * Data are raw facts. Information is the result of processing data to reveal its meaning.
  * To implement and manage a database, use a DBMS.
  * Database design defines the database structure.
  * A well-designed database facilitates data management and generates accurate and valuable information.
  * A poorly designed database can lead to bad decision making
  * Databases were preceded by file systems.
  * Limitations of file system data management: 
  * requires extensive programming
  * system administration complex and difficult
  * making changes to existing structures is difficult
  * security features are likely to be inadequate
  * independent files tend to contain redundant data
  * DBMS’s were developed to address file systems’ weaknesses


  
