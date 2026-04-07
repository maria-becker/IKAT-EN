# **Implicit Knowledge in Argumentative Texts: An Annotated Corpus (IKAT-EN)**

**Maria Becker, Katharina Korfhage, Anette Frank**  

[![Paper](https://img.shields.io/badge/Paper-LREC%202020-blue)](https://aclanthology.org/2020.lrec-1.282/)  
[![Dataset](https://img.shields.io/badge/Type-Annotated%20Corpus-orange)]()  

---

## 📄 Paper

**Implicit Knowledge in Argumentative Texts: An Annotated Corpus**  
Proceedings of the **12th Language Resources and Evaluation Conference (LREC 2020)**, Marseille, France  

👉 https://aclanthology.org/2020.lrec-1.282/  


---

## 📚 Citation

If you use **IKAT-EN** in your research, please cite:

```bibtex
@inproceedings{becker-etal-2020-ikat,
  title     = {Implicit Knowledge in Argumentative Texts: An Annotated Corpus},
  author    = {Becker, Maria and Korfhage, Katharina and Frank, Anette},
  booktitle = {Proceedings of the 12th Language Resources and Evaluation Conference (LREC)},
  year      = {2020},
  pages     = {2316--2324},
  address   = {Marseille, France},
  publisher = {European Language Resources Association}
}
```

---

## 📄 Short Project Description / Abstract

When speaking or writing, people omit information that seems clear and evident, such that only part of the message is expressed in words.  
Especially in argumentative texts it is very common that (important) parts of the argument are implied and omitted.  

We hypothesize that for argument analysis it will be beneficial to reconstruct this implied information.  
As a starting point for filling such knowledge gaps, we build a corpus consisting of high-quality human annotations of missing and implied information in argumentative texts.  

To learn more about the characteristics of both the argumentative texts and the added information, we further annotate the data with semantic clause types and commonsense knowledge relations.  

The outcome of our work is a carefully designed and richly annotated dataset, the **IKAT-EN corpus**.  

An in-depth analysis of characteristic distributions and correlations of the assigned labels can be found in our paper.  

> ⚠️ Please cite this paper when using IKAT-EN.

---

## 🧠 Annotation of Implicit Knowledge

The annotations are performed on sentence pairs from the Microtext corpus (the English version, Peldszus/Stede 2015).  

Each microtext is a short, dense argument consisting of roughly five elementary units of argumentation, so called **argumentative units** (Peldszus and Stede, 2015).  

We presented all sentence pairs to our annotators that are either adjacent or stand in an argumentative relation according to the argumentation graph.  
There are **719 such sentence pairs in 112 texts** in the corpus.  

We asked our annotators to:
- detect whether the connection between the pair of units is made fully explicit by the text  
- if not, explain the missing connection by providing one or more sentences  

The annotators were instructed:
- to add **as few sentences as possible**  
- to keep sentences **very simple** (if possible one fact per sentence)  
- to retrieve the **minimal amount of information needed**  
- to avoid overly detailed explanations  

Two expert annotators with a linguistic background produced two versions of the implicit knowledge.  
These served as the basis for the final **gold standard**, produced by another expert annotator (one of the authors), which is released here.  

---

## 🏷️ Annotation of Semantic Clause Types

Annotators labeled argumentative units and inserted sentences with **semantic clause types** (Smith 2003; Friedrich et al. 2016):

- **states** → describe specific properties of individuals  
- **events** → things that happen or have happened  
- **generic sentences** → predicates over classes or kinds  
- **generalizing sentences** → describe regularly occurring events or habits  

Annotations were performed independently by two trained annotators.  
A third expert annotator assigned the **GOLD label**.  

---

## 🔗 Annotation of ConceptNet Relations

To gain further insight into the type of knowledge covered by the argumentative texts and the annotations of implicit knowledge, we annotate both with **ConceptNet relation types** such as:

- `PartOf`  
- `Causes`  
- `IsA`  

The annotation was performed by:
- two annotators in parallel  
- one expert annotator assigning the **GOLD label**  

---

## 📁 Data Format

We provide **one TSV file per microtext**, structured as follows:

### Argumentative Units

- First lines display the argumentative units (`e-1` to `e-n`)  
- One line per unit  
- Each unit includes:
  - semantic clause types  
  - ConceptNet relations (GOLD version)  

**Notes:**

- Multiple clauses → separated by `/`  
  - Example: `STATE/GENERIC`  

- ConceptNet relations format:  
  - `concept1, concept2 (relation)`  
  - Example: `dog owners, negligent (HasProperty)`  

- Multiple relations → separated by `/`  

---

### Implicit Knowledge Annotations

Following lines contain annotations for sentence pairs:

| Column | Description |
|--------|------------|
| 1 | Argument pair (e.g. `e1-e3`) |
| 2 | Adjacency information |
| 3 | Argumentative relation |
| 4 | Number of inserted sentences |
| 5+ | Inserted sentences with annotations |

Inserted sentences include:
- semantic clause types  
- ConceptNet relations  

(all formatted as described above)

---

## 📘 Additional Resources

We release the **annotation manual** together with the corpus.  
The annotation process is described in more detail in Becker et al. (2020).  

---

## 📚 References

- Becker, M., Staniek, M., Nastase, V., Frank, A. (2017): *Enriching Argumentative Texts with Implicit Knowledge*. International Conference on Natural Language & Information Systems (NLDB).  

- Annemarie Friedrich, Alexis Palmer, and Manfred Pinkal. 2016. *Situation entity types: automatic classification of clause-level aspect*. Proceedings of ACL 2016.  

- Andreas Peldszus and Manfred Stede. 2015. *An annotated corpus of argumentative microtexts*. Proceedings of the First European Conference on Argumentation.  

- Carlota S. Smith. 2003. *Modes of discourse: The local structure of texts*. Cambridge University Press.  
