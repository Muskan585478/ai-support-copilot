Day 1 & Day 2 — Interview Prep Answers
Simple, concise answers in English that you can speak directly in an interview.
Day 1: Database, Security & AI
1. PostgreSQL vs MongoDB — when would you choose each?
- PostgreSQL: When data is structured, relationships are important, and I need SQL queries and joins.
- MongoDB: When data is flexible or semi-structured, and documents may have different fields.
Example: Banking system → PostgreSQL; flexible product catalog → MongoDB.

2. Why is hardcoding API keys wrong?

Hardcoding API keys can expose secrets if I upload my code to GitHub. Someone could misuse them and cause security or financial issues. I store keys in a .env file and add it to .gitignore.

3. What is an embedding?

An embedding converts text into a numerical vector that represents its meaning. Texts with similar meanings usually have vectors close to each other.

Example: “car” and “automobile” may have similar embeddings.

4. What is RAG, and why is it better than using only an LLM?

RAG stands for Retrieval-Augmented Generation. It retrieves relevant information from external documents and provides it to the LLM to generate an answer. It can improve accuracy and reduce hallucinations by grounding answers in relevant information.

5. Difference between .env and .env.example?
- .env: Contains actual environment variables and secret values; it should not be committed to Git.
- .env.example: Contains placeholder values showing which variables are required; it is safe to share.
Example: API_KEY=your_api_key_here

Day 2: SQL & Vector Search
1. INNER JOIN vs LEFT JOIN?
- INNER JOIN: Returns only rows that match in both tables.
- LEFT JOIN: Returns all rows from the left table and matching rows from the right table. Unmatched right-side values become NULL.
Example: To show all students, including those without bookings, I use LEFT JOIN. To show only students who have bookings, I use INNER JOIN.
SELECT s.name, b.booking_id
FROM students s
LEFT JOIN bookings b ON s.id = b.student_id;


2. What is an index, and why not create one on every column?

An index is like a book's index: it helps find data faster. However, indexes require extra storage and slow down INSERT, UPDATE, and DELETE operations. I create indexes on columns frequently used for searching, joining, or sorting.

3. What does ON DELETE CASCADE do?

It automatically deletes related child rows when the referenced parent row is deleted. It can be dangerous if deleting one parent unintentionally removes many important records.

4. How do embeddings find similar text?

Text is converted into vectors, and a similarity or distance measure compares them. In PostgreSQL with pgvector, <=> calculates cosine distance. A smaller cosine distance means the vectors are more similar.

5. Primary key vs foreign key?
- Primary key: Uniquely identifies each row in a table.
- Foreign key: References a key in another table to establish a relationship and enforce referential integrity.
Example: students.id is a primary key; bookings.student_id is a foreign key.

6. What happens if I forget WHERE in an UPDATE or DELETE query?

Without WHERE, the query affects all rows in the table.
UPDATE students SET status = 'Inactive';


This updates every student's status. I always verify the condition and affected rows before executing destructive queries.