# AI4ED Lex - A Lexical Database for Skills Mapping

In the study of document classification within a corpus, the probability of encountering a specific term in a particular document category is modeled using a Poisson distribution. The relevant equation is given by:

\[ \text{(eq. 1) Poisson distribution: } p(n | N, f) = e^{-Nf} \cdot \frac{(Nf)^n}{n!} \]

Where:
- \( n \) is the count of the term in question within a category (e.g., counts of 'Node.js' in job descriptions).
- \( N \) represents the total number of terms found in that category.
- \( f \) stands for the term's frequency across the entire corpus, estimated through random sampling of Wikipedia articles (i.e., term count in the corpus divided by the total term count in the corpus).

To circumvent floating-point errors, eq. 1 can be reformulated in logarithmic terms:

\[ \text{(eq. 2) } \ln p(n | N, f) = -Nf + n \ln(Nf) - \ln(n!) \]

For large values of \( n \), \( n! \) is computed using Stirling's approximation. Utilizing this approach, a collection of terms, termed "Discriminating Terms" for a subject, can be established. These terms function as linear discriminants and are employed to construct a likelihood statistic that integrates these features to categorize an abstract. This methodology extends the classical model by Mosteller and Wallace in their work on authorship disputes of The Federalist Papers.




