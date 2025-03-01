# Current Prompt
Use the below prompt to generate python objects for personas and responses:

---

### Building Personas
I need you to adopt multiple distinct, fixed personalities for a survey study. Each personality should respond as if it were a genuine human survey respondent, with consistent traits and behaviors throughout the entire survey, regardless of the questions asked. Output your results for each persona in the form of python objects conforming to this dataclass, using the comments to guide attribute selection:

```python
@dataclass
class Persona:
    model: str # your large language model name. Choose from ['GPT-3.5', 'GPT-4', "DeepSeek', 'Gemini']. If you do not see your model in this list, set the model attribute to your model name. 
    name: str # provide a first and last name to maintain uniqueness across respondents
    age: int 
    gender: str # gender = ["Male", "Female", "Non-binary", "Prefer not to say", "Other"]
    race: str # race = ["White", "Black or African American", "Asian", "Native American or Alaska Native", "Native Hawaiian or Other Pacific Islander", "Mixed", "Other", "Prefer not to say"]
    ethnicity: str # ethnicity = ["Hispanic or Latino", "Not Hispanic or Latino", "Other", "Prefer not to say"]
    country: str # use ISO 3166-1 for country name
    native_language: str # choose one
    education_level: str # education_levels =  ["High School Diploma", "Some College (no degree)", "Associate's Degree", "Bachelor's Degree", "Master's Degree", "PhD", "Postdoctoral Research", "Other"]
    socioeconomic_background: str # socio_economic_backgrounds = ["Low Income", "Lower-Middle Income", "Middle Income", "Upper-Middle Income", "High Income", "Other"]
    years_of_experience: int # years of software engineering experience specifically
    primary_programming_languages: List[str]
    type_of_employer: str # type_of_employer = ["Public Sector", "Private Sector", "Non-profit", "Self-employed", "Academia", "Startup", "Freelance", "Other"]
    industry_domain: str # industry_domains = ["Finance", "Healthcare", "Technology", "Retail", "Manufacturing", "Education", "Government", "Energy", "Transportation", "Other"]
    team_size: int # number of people on team
    remote: bool 
    preferred_methodology: str # preferred_methodologies = ["Agile", "Waterfall", "Scrum", "Kanban", "Lean", "DevOps", "Hybrid", "Other"]
    exposure_to_international_teams: bool
    personality_type: str # Use Myers-Briggs: personality_types = ["ISTJ", "ISFJ", "INFJ", "INTJ", "ISTP", "ISFP", "INFP", "INTP", "ESTP", "ESFP", "ENFP", "ENTP", "ESTJ", "ESFJ", "ENFJ", "ENTJ"]
    workload: str # workload = ["Very Light", "Light", "Moderate", "Heavy", "Very Heavy"]
    open_source_involvement: bool
    familiarity_with_emerging_tech: str # familiarity_with_emerging_tech = ["Not Familiar", "Slightly Familiar", "Moderately Familiar", "Very Familiar", "Expert"]
    academic_background: str # academic_backgrounds = ["Computer Science", "Engineering", "Mathematics/Statistics", "Business", "Arts/Humanities", "Social Sciences", "Biology/Medicine", "Other"]
    company_size: str # company_size = ["1-10 employees", "11-50 employees", "51-200 employees", "201-500 employees", "501-1000 employees", "1001-5000 employees", "5001+ employees"]
    hobbies: List[str] # put whatever you want here
    learning_style: str # learning_styles = ["Visual", "Auditory", "Reading/Writing", "Kinesthetic", "Social", "Solitary", "Other"]
    comfort_with_ambiguity: Union[str, int] # comfort_with_ambiguity = ["Not Comfortable", "Slightly Comfortable", "Moderately Comfortable", "Very Comfortable", "Extremely Comfortable"]
```

Do not copy the data class or provide any imports. Simply generate the objects. 

Generate 100 personas.

TODO: Match the bove approach to generate Survey response objects.

### StackOverflow Survey Questions:

answer these 10 questions persona wise , "**questions omitted here **", give each persona as much character as possible, the questions maybe multiple choice based, you may choose from the choice or you may also give a totally novel responses, the options are just there for easier tracking of metrics and should not affect your responses as personas in any manner, stick to your personas character traits

 —----------------------------------------------------------------------------

1. Which of the following best describes the highest level of formal education that you’ve completed? Primary/elementary school Secondary school Some college/uni study w/o ear… Associate degree Bachelor’s degree Master’s degree Pro. Degree Something else
2. How do you learn to code? Select all that apply. Other online resources Books / Physical media E-courses or Certification School On-the-job training Colleague Coding Bootcamp A friend or family member
3. What online resources do you use to learn to code? Select all that apply Technical documentation Stack Overflow Written Tutorials Blogs How-to videos Video-based E-courses Online books Social Media AI Written-based E-courses Interactive tutorial Online challenges Coding sessions Certification videos Auditory material Games that teach programming
4. What is the source of the technical documentation you use most often to learn to code? Select all that apply. API document and/or SDK document User guides or README files found in the source repository Traditional public search engine First-party knowledge base AI-powered search/dev tool AI-powered search/dev tool
5. Including any education, how many years have you been coding in total? Less than 1 year 1 to 4 years 5 to 9 years 10 to 14 years 15 to 19 years 20 to 24 years 25 to 29 years 30 to 34 years 35 to 39 years 40 to 44 years 45 to 49 years More than 50 years
6. NOT including education, how many years have you coded professionally (as a part of your work)? Less than 1 year 1 to 4 years 5 to 9 years 10 to 14 years 15 to 19 years 20 to 24 years 25 to 29 years 30 to 34 years 35 to 39 years 40 to 44 years 45 to 49 years More than 50 years
7. NOT including education, how many years have you coded professionally (as a part of your work)? (Ask this question and question 8 at the same time.) Senior Executive Manager Dev Advocate Product Manager DB admin Edu PM Ent. Designer Research & Dev role Embed Dev Experience SRE Sci. Cloud infra. Engineer Sys Back-end DevOps Specialist Full-stack Data Engineer Marketing or sales pro. Security pro. Hardware Mobile Blockchain Games Academic researcher Data sci. or ML specialist QA Dev, AI Data/Biz Front-end Student
8. Which of the following describes your current job, the one you do most of the time? Please select only one. Full-stack Back-end Student Front-end Ent. Mobile Embed Manager Academic researcher Data Engineer Data sci. or ML specialist DevOps Specialist Research & Dev role Senior Executive Games Cloud infra. Engineer Sys Dev, AI QA Data/Biz PM Edu Security pro. Sci. SRE Product Manager Blockchain Dev Experience Hardware Designer DB admin Dev Advocate Marketing or sales pro.
9. Where do you live? (Open-ended question. I think it’s just reporting on countries that were selected and left out the rest, so we should prompt it to select a country while still being realistic about where the engineer would be from.)
10. What is your age?
- Under 18 years old 
- 18-24 years old 
- 25-34 years old 
- 35-44 years old 
- 45-54 years old 
- 55-64 years old 
- 65 years or older 
- Prefer not to say

 —---------------------------------------------------------------------------