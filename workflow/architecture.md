# Technical Architecture

## Production Data Flow

1. **Tally — Story Intake**  
   The participant submits an unstructured lived-experience story.

2. **Make.com — Workflow Trigger and Orchestration**  
   The Tally submission triggers the working scenario.

3. **Google Sheets — Participant and Workflow Record**  
   The workflow creates and updates the participant record and processing status.

4. **Google Docs — Reasoning Instructions**  
   The workflow retrieves the Human Potential Recognition™ reasoning instructions used for the Gemini request.

5. **Gemini 2.5 Pro — Core Reasoning**  
   Gemini receives the participant story and governed instructions, recognises meaningful patterns of observable contribution, and generates the structured Human Potential Reflection™ output.

6. **Make.com / JSON — Output Processing**  
   The structured Gemini response is parsed for downstream document generation.

7. **Google Sheets — Workflow Update**  
   The generated reflection and workflow status are recorded.

8. **Google Docs — Reflection Generation**  
   A personalised Human Potential Reflection™ document is created from the template.

9. **Google Drive — File Handling and Storage**  
   The completed reflection is stored for delivery.

10. **Gmail — Participant Delivery**  
    The completed reflection is sent to the participant.

11. **Tally + Make.com — Feedback**  
    Participant feedback is captured separately and used to evaluate and improve the experience.

## AI Decision Boundary

**Gemini decides/interprets:**
- patterns supported by the participant's story;
- observable contribution reflected in the narrative;
- hypotheses about human potential;
- synthesis and reflective questions.

**Human responsibility:**
- Constitution and reasoning boundaries;
- participant-experience design;
- workflow monitoring and exception handling;
- evaluation of pilot feedback;
- architecture and strategic direction.

**Participant responsibility:**
- ownership of personal meaning and interpretation.

## Implementation

The hackathon implementation is intentionally low-code. The working orchestration is represented by the sanitised Make.com blueprint in `make-scenario/`.
