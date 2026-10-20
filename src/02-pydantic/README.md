# 02 · Pydantic for Agents

> **Notes:** [04 · Pydantic for AI Agents — Data Validation](../../docs/notes/04-pydantic-data-validation.md)

Data validation as the foundation for **structured LLM output**, **tool schemas** and **graph state**.

| Section in [`pydantic_for_agents.ipynb`](pydantic_for_agents.ipynb) | Concept |
|---|---|
| Problem without Pydantic | Hand-written `type()` / range checks duplicated per function |
| How to use Pydantic | `BaseModel` → `Model(**raw)` → pass the validated object |
| Little complex | `List[str]`, `Dict[str, str]` |
| Required & optional | `Optional[...] = None`, defaults |
| Data validation | `EmailStr`, `AnyUrl`, `Field(gt, lt, max_length)`, `Annotated` metadata, `strict=True` |
| Field validator | `@field_validator` (bank-domain email check, upper-case name) |
| Model validator | `@model_validator(mode="after")` (age > 60 requires an emergency contact) |
| Computed fields | `@computed_field` BMI |
| Nested models | `Address` inside `PatientData` |
| Serialization | `model_dump()`, `model_dump_json()` |

```bash
conda create -n pydantic-demo python=3.11 -y && conda activate pydantic-demo
pip install -r requirements.txt          # pydantic[email]>=2 (EmailStr needs email-validator)
```
