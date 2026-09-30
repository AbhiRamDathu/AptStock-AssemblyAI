# AptStock AI — Voice Inventory Copilot

> **From inventory signals to spoken decisions to controlled replenishment.**

AptStock is a **voice-native inventory intelligence copilot for multi-SKU retailers**.

It connects real store sales data, demand forecasting, inventory risk detection, prioritized recommendations, and a controlled reorder workflow to a real-time conversational interface powered by **AssemblyAI's Voice Agent API**.

Instead of forcing a store manager to search through hundreds or thousands of SKUs, AptStock lets them ask:

> **“What needs my attention?”**

and continue naturally:

> **“Why?”**  
> **“How much should I reorder?”**  
> **“Prepare the reorder.”**  
> **“Change it to 200 units.”**  
> **“Cancel that reorder.”**  
> **“I need help from someone.”**

The important part is that voice is not a separate chatbot sitting beside the inventory system.

**Voice is the operating layer over the inventory decision workflow.**

---

## The Problem

Multi-SKU retailers have a simple but difficult operational problem:

**There are too many products and too many decisions for a manager to inspect manually.**

A store may have:

- Fast-moving products approaching stockout
- Products that need replenishment
- Slow-moving products
- Excess inventory
- Different demand patterns across SKUs
- Different lead times
- Different safety-stock requirements
- Limited attention from store staff

Traditional workflows make the manager search through dashboards, spreadsheets, POS reports, and purchase lists.

The result is a gap between:

**data → decision → action**

AptStock is designed to close that gap.

---

# What AptStock Does

AptStock transforms store sales data into an inventory decision workflow:

```text
STORE / POS DATA
       │
       ▼
DATA NORMALIZATION
       │
       ▼
DEMAND & INVENTORY INTELLIGENCE
       │
       ├── Forecast
       ├── Sales patterns
       ├── Stock risk
       ├── Safety stock
       ├── Lead-time considerations
       └── Replenishment recommendation
       │
       ▼
PRIORITIZED INVENTORY ACTIONS
       │
       ▼
ASSEMBLYAI VOICE AGENT
       │
       ├── Ask
       ├── Understand
       ├── Explain
       ├── Prepare
       ├── Correct
       └── Cancel
       │
       ▼
CONTROLLED REORDER WORKFLOW

The manager does not have to navigate the entire inventory system to discover what matters.

They can ask.

Why Voice Matters

AptStock is not using voice merely to replace a text input box.

The voice interface is connected to the actual inventory workflow.

The flow is:

SPEECH
  ↓
ASSEMBLYAI REAL-TIME VOICE AGENT
  ↓
TOOL CALL
  ↓
APTSTOCK INVENTORY CONTEXT
  ↓
INVENTORY / FORECAST / PRIORITY LOGIC
  ↓
STRUCTURED RESULT
  ↓
VOICE EXPLANATION
  ↓
CONTROLLED ACTION

This makes AssemblyAI part of the operational interaction layer rather than simply a transcription service.

The Voice Agent API provides the real-time conversational layer, including speech recognition, agent reasoning, speech output, tool calling, turn detection and interruption handling.

The Core AptStock Experience
1. Ask

A manager can ask:

“What inventory needs attention?”

AptStock uses the selected store context and inventory intelligence to identify products requiring attention.

2. Understand

The manager can ask follow-up questions naturally:

“Why does that product need attention?”

“How much should I reorder?”

“What is my current stock?”

“Which product should I handle first?”

The goal is to turn an inventory dashboard into a conversational decision interface.

3. Explain

A recommendation should not be treated as an unexplained AI number.

AptStock's inventory intelligence can use signals such as:

Historical sales
Demand patterns
Forecasts
Safety-stock logic
Lead-time information
Current-stock information when available
Inventory risk
Replenishment requirements

The voice layer exposes these decisions conversationally.

The intended interaction is:

MANAGER
Why should I reorder this?

APTSTOCK
Because the product is showing inventory risk based on
its sales and replenishment signals.

The objective is simple:

The system should explain the business decision using the data available to it rather than inventing an explanation.

4. Prepare — Don't Blindly Execute

AptStock separates preparing a reorder from actually placing a supplier order.

A voice request such as:

“Prepare a reorder for Heritage Curd Cup.”

creates a controlled reorder draft.

The workflow is intentionally bounded:

VOICE INTENT
     ↓
VALIDATE
     ↓
PREPARE REORDER DRAFT
     ↓
PENDING CONFIRMATION

The assistant is instructed not to claim that an order was placed when the application has only prepared a draft.

This distinction matters for trust.

5. Correct

Voice interactions are conversational.

Managers change their minds.

For example:

Manager:
Prepare a reorder for Heritage Curd Cup.

AptStock:
I've prepared the reorder draft.

Manager:
Change the quantity to 200.

AptStock:
The reorder quantity has been updated.

The quantity is treated as part of the controlled action rather than as an independent conversational statement.

The intended design is:

DRAFT
  ↓
CHANGE
  ↓
UPDATED DRAFT
  ↓
NEW CONFIRMATION REQUIRED

This prevents an earlier approval from silently becoming approval for a materially different action.

6. Cancel

AptStock also supports cancellation of a pending reorder draft.

Example:

“Cancel the reorder for Heritage Curd Cup.”

The backend only cancels a reorder that is in the pending-confirmation state.

Conceptually:

PENDING_CONFIRMATION
        │
        ▼
     CANCEL
        │
        ▼
     CANCELLED

The system does not pretend that cancellation of a draft is the same as cancellation of an already-completed supplier transaction.

7. Human Assistance

Not every situation should remain automated.

AptStock supports a human-assistance request.

Example:

“I need to speak with someone.”

The application persists a human assistance request so the AptStock team can follow up.

The assistant does not claim that a live human telephone transfer occurred unless an actual telephony transfer is implemented.

Multi-SKU Intelligence

AptStock is designed for the reality of multi-SKU retail.

The system does not require a manager to manually inspect every product.

Instead, it can identify products that deserve attention and surface prioritized inventory actions.

This creates a different interaction model:

Traditional workflow:

SKU 1 → inspect
SKU 2 → inspect
SKU 3 → inspect
SKU 4 → inspect
...
SKU N → inspect


AptStock workflow:

ALL STORE DATA
      ↓
INVENTORY INTELLIGENCE
      ↓
PRIORITIZED PRODUCTS
      ↓
MANAGER ASKS
      ↓
VOICE DECISION

The objective is to focus human attention where the inventory system identifies meaningful risk or replenishment needs.

Why AptStock Is More Than a Voice Wrapper

A generic voice assistant can answer questions.

AptStock connects voice to a domain-specific decision system.

Generic Voice Assistant

Speech
  ↓
LLM
  ↓
Answer


AptStock

Speech
  ↓
AssemblyAI Voice Agent
  ↓
Store Context
  ↓
Inventory Intelligence
  ↓
Forecast / Risk / Recommendation
  ↓
Explanation
  ↓
Controlled Reorder Draft
  ↓
Correction / Cancellation / Assistance

The product's core value therefore remains useful even without the voice layer.

Voice makes that inventory intelligence directly accessible during the manager's workflow.

Application Architecture
                         ┌─────────────────────┐
                         │       Manager       │
                         │      Voice Input    │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │    AssemblyAI       │
                         │    Voice Agent API  │
                         │                     │
                         │ STT / Reasoning /   │
                         │ TTS / Turn Taking / │
                         │ Tool Calling        │
                         └──────────┬──────────┘
                                    │
                              tool.call
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │   AptStock Voice    │
                         │    Action Layer     │
                         └──────────┬──────────┘
                                    │
                  ┌─────────────────┼──────────────────┐
                  │                 │                  │
                  ▼                 ▼                  ▼
          Inventory Query      Reorder Draft       Assistance
                  │                 │                  │
                  ▼                 ▼                  ▼
          AptStock Engine      Backend API        MongoDB
                  │                 │
                  └────────┬────────┘
                           ▼
                  Structured Tool Result
                           │
                           ▼
                    AssemblyAI Agent
                           │
                           ▼
                    Spoken Response
Voice Tools

The current voice workflow exposes domain-specific tools including:

get_inventory_alerts

Retrieves the current inventory context for the selected store, including relevant inventory and priority information.

prepare_reorder

Creates a controlled reorder draft after validating:

Store context
SKU
Quantity

The tool is explicitly instructed not to place an order without confirmation.

cancel_reorder

Cancels a pending reorder draft.

transfer_to_human

Creates a persisted human-assistance request when the manager needs human help.

Voice Safety Design

AptStock treats voice actions differently from ordinary conversation.

The design principles are:

1. Application context over model-generated context

The active store is resolved from the application context rather than blindly trusting a model-generated store value.

2. Validate before action

The voice model can propose:

store
sku
quantity

but the application validates those values before preparing the reorder.

3. Draft before commitment

Preparing a reorder is separate from actually placing an external supplier order.

4. Confirmation matters

A materially changed action should not inherit an earlier confirmation.

5. Cancellation is explicit

A pending reorder can be cancelled without pretending that an already-completed external transaction was reversed.

6. Interruptions are first-class events

If the manager interrupts the assistant, stale audio is flushed and stale pending tool results are discarded.

7. Human escalation is persisted

Human assistance becomes a real backend request rather than an empty conversational promise.

Interruption / Barge-In Handling

Natural voice interaction requires interruption handling.

AptStock handles interruption at the browser playback layer.

When the manager begins speaking while AptStock is speaking:

USER SPEAKS
    ↓
INTERRUPTION DETECTED
    ↓
FLUSH CURRENT PLAYBACK
    ↓
INVALIDATE STALE AUDIO
    ↓
DISCARD INTERRUPTED TOOL RESULTS
    ↓
LISTEN AGAIN

The implementation also uses playback-generation tracking so asynchronous audio work belonging to an older response cannot simply re-enter playback after an interruption.

This is important because a voice assistant that continues speaking after the manager has taken the floor feels broken even if its underlying model is correct.

Evidence-Oriented Product Philosophy

AptStock is built around a simple principle:

The voice agent should explain inventory decisions from AptStock's actual application state, not invent business facts.

The architecture therefore separates:

CONVERSATION

from:

BUSINESS DATA

and:

ACTION EXECUTION

The model interprets the conversation.

The AptStock application owns the inventory state.

The backend owns the action state.

This separation is central to making a voice interface trustworthy for operational workflows.

Business Value

For a multi-SKU retailer, the value is not “having a voice chatbot.”

The value is reducing the distance between:

WHAT IS HAPPENING?
        ↓
WHY IS IT HAPPENING?
        ↓
WHAT SHOULD I DO?
        ↓
HOW MUCH?
        ↓
SHOULD I ACT?

AptStock brings these questions into one conversational workflow.

Potential business outcomes include:

Faster identification of products needing attention
Less manual SKU-by-SKU inspection
Faster access to inventory explanations
More accessible replenishment recommendations
A controlled path from recommendation to reorder preparation
Better operational visibility for store managers

AptStock is designed around a practical retail problem:

helping a manager decide what inventory action deserves attention next.

Why Multi-SKU Retail Is the Core Use Case

AptStock is intentionally designed around multi-SKU stores rather than a single-product demonstration.

The system is intended to operate over a store's broader product catalog and prioritize attention rather than forcing the manager to manually interrogate every SKU.

The voice experience then sits on top of that prioritization.

That creates:

MANY PRODUCTS
      ↓
INVENTORY INTELLIGENCE
      ↓
FEWER HIGH-VALUE DECISIONS
      ↓
VOICE ACCESS
Technology Stack
Voice
AssemblyAI Voice Agent API
Real-time WebSocket communication
Streaming microphone audio
Real-time transcription
Agent speech output
Tool calling
Semantic turn detection
Barge-in / interruption handling
Frontend
React
Browser Web Audio APIs
Real-time WebSocket client
Voice state management
Inventory dashboard integration
Backend
FastAPI
Python
MongoDB
Pandas
NumPy
Forecasting / inventory intelligence services
Deployment
Production frontend
Production FastAPI backend
Production database
Real AssemblyAI Voice Agent integration
Production Workflow
1. Retailer uploads store sales data
                ↓
2. AptStock validates and normalizes the data
                ↓
3. Inventory intelligence is generated
                ↓
4. Products requiring attention are prioritized
                ↓
5. Manager opens the voice assistant
                ↓
6. Manager asks about inventory
                ↓
7. AssemblyAI handles the real-time conversation
                ↓
8. AptStock tools provide actual application data
                ↓
9. Manager asks why / how much / what next
                ↓
10. AptStock prepares a controlled reorder draft
                ↓
11. Manager can correct or cancel the draft
                ↓
12. Human assistance can be requested when needed
Example End-to-End Conversation
Manager:
What inventory needs my attention?

AptStock:
Heritage Curd Cup is one of the products requiring attention.

Manager:
Why?

AptStock:
It is showing inventory risk based on the available sales
and replenishment signals.

Manager:
How much should I reorder?

AptStock:
The current AptStock recommendation is [recommended quantity]
based on the available inventory and demand information.

Manager:
Prepare the reorder.

AptStock:
I've prepared a reorder draft. Confirmation is required.

Manager:
Change the quantity to 200.

AptStock:
The reorder quantity has been updated to 200 units.
A new confirmation is required for the changed action.

Manager:
Actually, cancel it.

AptStock:
The pending reorder has been cancelled.

Manager:
I need help from someone.

AptStock:
I've submitted a request for an AptStock team member to assist you.

The exact spoken values come from the live application state.

What Makes This Different

The central idea is not:

“Talk to your dashboard.”

It is:

“Operate your inventory decision workflow through voice.”

AptStock combines:

REAL STORE DATA
        +
INVENTORY INTELLIGENCE
        +
MULTI-SKU PRIORITIZATION
        +
REAL-TIME VOICE
        +
EXPLAINABLE DECISIONS
        +
CONTROLLED ACTIONS
        +
INTERRUPTION HANDLING
        +
CANCELLATION
        +
HUMAN ESCALATION

The result is a voice-native operational interface for retail inventory.

Judging Criteria Alignment
1. Application of Technology
How effectively are the chosen models integrated?

AptStock uses AssemblyAI as the real-time conversational control layer.

The integration includes:

Real-time speech input
Speech understanding
Conversational agent reasoning
Spoken responses
Tool calling
Live inventory context
Reorder actions
Interruption handling
Barge-in behavior
Tool-result synchronization

The important architecture is:

Speech
  ↓
AssemblyAI
  ↓
Structured tool call
  ↓
AptStock backend / inventory intelligence
  ↓
Structured result
  ↓
AssemblyAI
  ↓
Speech

AssemblyAI is therefore integrated into the operational workflow rather than being used only as a transcription component.

2. Presentation

The product is demonstrated through a single coherent story:

UPLOAD
   ↓
UNDERSTAND
   ↓
ASK
   ↓
EXPLAIN
   ↓
RECOMMEND
   ↓
PREPARE
   ↓
CORRECT
   ↓
CANCEL / ESCALATE

The goal is to demonstrate a complete business workflow rather than a collection of disconnected features.

3. Business Value

AptStock targets a concrete operational problem:

helping multi-SKU retailers identify and act on inventory decisions faster.

Instead of requiring a manager to manually search through large product catalogs, AptStock prioritizes inventory attention and makes those decisions accessible conversationally.

The value is therefore tied directly to:

Inventory risk
Replenishment
Stockout prevention
SKU prioritization
Manager decision time
Controlled purchasing workflows
4. Originality

AptStock combines two traditionally separate interfaces:

INVENTORY INTELLIGENCE
+
VOICE ACTION

The voice assistant is not a generic productivity assistant.

Its domain is the inventory decision itself.

The manager can move from:

“What is wrong?”

to:

“Why?”

to:

“How much?”

to:

“Prepare it.”

to:

“Change it.”

to:

“Cancel it.”

without leaving the inventory workflow.

That combination of multi-SKU inventory intelligence and controlled voice interaction is the core product concept.

Design Principle

AptStock follows one central principle:

AI should make inventory decisions easier to access without making business actions less controlled.

Voice provides the natural interface.

AptStock provides the inventory intelligence.

The backend provides the action boundary.

The manager remains in control.

Repository Structure

A simplified representation:

aptstock/
│
├── frontend/
│   ├── VoiceAgent.jsx
│   ├── dashboard components
│   └── inventory / forecast UI
│
├── backend/
│   ├── app/
│   │   ├── routes/
│   │   │   ├── forecast_routes.py
│   │   │   ├── inventory_routes.py
│   │   │   └── voice_routes.py
│   │   │
│   │   ├── services/
│   │   │   └── database_service.py
│   │   │
│   │   └── middlewares/
│   │
│   └── requirements.txt
│
└── README.md
Key Voice Endpoints
GET
/api/inventory-alerts

POST
/api/inventory/prepare-reorder

POST
/api/inventory/cancel-reorder

POST
/api/inventory/request-human-assistance

These endpoints form the bridge between the conversational layer and the operational inventory workflow.

Reliability Philosophy

AptStock does not treat the language model as the final authority over inventory state.

The architecture follows:

AI PROPOSES
      ↓
APPLICATION VALIDATES
      ↓
BACKEND OWNS STATE
      ↓
ACTION IS CONTROLLED

This is especially important for quantities, SKU identity, store context, reorder drafts and cancellation.

Production Status

AptStock is deployed as a working production application with a live frontend, backend and AssemblyAI-powered voice workflow.

The final implementation has been validated through the project's end-to-end voice and inventory workflow tests.

The repository is provided so the architecture, implementation and integration can be inspected rather than treated as a black-box demo.

What AptStock Is Not

AptStock is not presented as:

A generic chatbot
A voice-only demo
A replacement for a retailer's entire ERP
An autonomous purchasing system
A system that invents inventory facts
A system that claims a supplier order was placed when only a draft was created

Instead, it is a:

Voice-native inventory decision copilot for multi-SKU retail.

The Core Loop
             ASK
              │
              ▼
         UNDERSTAND
              │
              ▼
          EXPLAIN
              │
              ▼
         RECOMMEND
              │
              ▼
           PREPARE
              │
              ▼
          CONFIRM
              │
       ┌──────┴──────┐
       │             │
       ▼             ▼
    CHANGE        CANCEL
       │
       ▼
  NEW CONFIRMATION

This is the workflow AptStock is designed to make conversational.

Built for the Manager, Not the Dashboard

AptStock's long-term interface vision is simple:

The inventory dashboard should remain available.

But the manager should not have to navigate the dashboard for every decision.

They should be able to ask:

“What matters right now?”

and then continue the conversation until they understand the decision.

That is the purpose of the AptStock voice layer.

Final Statement

AptStock turns inventory intelligence into a conversation and a controlled action workflow.

It combines:

multi-SKU inventory intelligence

with

real-time AssemblyAI voice interaction

to create a practical retail copilot that can:

identify → explain → recommend → prepare → correct → cancel → escalate.

The goal is not to make voice sound impressive.

The goal is to make a store manager's next inventory decision easier, faster, and more controlled.

Built With

AssemblyAI Voice Agent API · React · FastAPI · Python · MongoDB · Pandas · NumPy

AptStock AI
