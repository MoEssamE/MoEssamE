## Mohamed Essam

I build tooling for getting off Oracle ADF.

ADF applications are still running payroll, licensing and case management at banks, ministries and
telcos. The people who wrote them have moved on, JDeveloper is a hard sell to new hires, and the
first question — *how much of this can actually be migrated?* — usually gets answered by a
consultant reading XML for three weeks.

**[adfmig](https://github.com/trippysolutions/adfmig)** answers it in about a minute. Point it at
an ADF application and it reads the entity objects, view objects, application modules, page
definitions and the security policy, then tells you what a migration to Spring Boot would actually
involve: which endpoints carry across, which business logic has to be rewritten by hand, and where
the source does not say enough to migrate correctly.

It runs entirely on your machine. Nothing is uploaded, no model is consulted, and the same input
produces the same output every time — which matters when the code it is reading is the reason your
organisation has a compliance department.

The assessment half is MIT licensed. Generating the Spring Boot project is
[adfmig Pro](https://trippysolutions.com).

```
brew install openjdk@21   # or any JDK 21
java -jar adfmig.jar start
```

**What it is tested against:** several hundred real ADF applications, generated, compiled and
started against a live Oracle database — plus one customer estate of fifteen. Every defect it has
ever had was found by running the output and comparing it against real rows, never by reading code.

**It does not migrate the front end.** ADF Faces is a server-side component framework with no
equivalent in Spring Boot, and most ADF applications are mostly screens. The tool says so before
you invest in it rather than after.

---

Trippy Solutions · [trippysolutions.com](https://trippysolutions.com)
