# AptStock AI — Voice Inventory Copilot

> **Predictive replenishment operated conversationally.**

AptStock is a voice-powered demand forecasting and inventory optimization copilot for multi-SKU retailers.

It turns store sales and inventory data into a prioritized answer to a practical operational question:

> **What needs attention now, why, and what should happen next?**

AptStock combines demand forecasting, inventory-risk analysis, safety-stock logic, multi-SKU prioritization, replenishment recommendations, and a conversational voice interface powered by **AssemblyAI's Voice Agent API**.

The key idea is simple:

**Voice is not a chatbot beside the inventory system.  
Voice is the operating layer over the inventory decision workflow.**

---

## The Problem

Retailers can have hundreds or thousands of SKUs generating a continuous stream of sales and inventory data.

The problem is not simply having the data.

The problem is turning that volume of information into the **next operational decision**.

A manager may need to determine:

- Which products need attention?
- Which products are approaching inventory risk?
- Why does a product need attention?
- What demand should be expected?
- How much should be replenished?
- Which products should be prioritized?
- Should a reorder be prepared?
- What happens if the manager changes the quantity?
- What happens if the manager changes their mind?
- When should a human take over?

Traditional workflows often require moving between sales reports, spreadsheets, dashboards, inventory screens, and purchasing workflows.

AptStock is designed to reduce that distance.

### From data to decision

```text
REAL STORE DATA
       ↓
DEMAND FORECAST
       ↓
INVENTORY OPTIMIZATION
       ↓
MULTI-SKU PRIORITY
       ↓
VOICE REASONING
       ↓
CONTROLLED REORDER
       ↓
CHANGE / CANCEL
       ↓
INTERRUPTION SAFETY
       ↓
STATE VERIFICATION

This is the core AptStock workflow.

What AptStock Does

AptStock transforms retail data into prioritized inventory decisions.

STORE / POS DATA
       ↓
DATA NORMALIZATION
       ↓
DEMAND & INVENTORY INTELLIGENCE
       ├── Sales patterns
       ├── Demand forecasting
       ├── Inventory risk
       ├── Safety-stock logic
       ├── Lead-time considerations
       └── Replenishment recommendations
       ↓
MULTI-SKU PRIORITIZATION
       ↓
ASSEMBLYAI VOICE AGENT
       ↓
EXPLANATION + CONTROLLED ACTION

Instead of forcing a manager to manually inspect every SKU, AptStock surfaces products that deserve attention and makes the resulting inventory intelligence accessible through natural conversation.

Why Voice Matters

AptStock does not use voice merely as a different input field.

The voice layer is connected to the actual inventory workflow.

A manager can move naturally from:

"What needs my attention?"

to:

"Why?"

then:

"How much should I reorder?"

then:

"Prepare the reorder."

and, if necessary:

"Change it to 200 units."

or:

"Cancel that reorder."

The conversation therefore becomes part of the operational workflow rather than a separate question-answering experience.

The Complete Voice-to-Action Loop
MANAGER SPEAKS
      ↓
ASSEMBLYAI VOICE AGENT
      ↓
UNDERSTAND INTENT
      ↓
APTSTOCK INVENTORY CONTEXT
      ↓
DOMAIN-SPECIFIC TOOL
      ↓
INVENTORY / FORECAST / PRIORITY LOGIC
      ↓
STRUCTURED RESULT
      ↓
VOICE EXPLANATION
      ↓
CONTROLLED ACTION
      ↓
STATE UPDATE
      ↓
NEXT CONVERSATIONAL DECISION

The result is a bridge between predictive retail intelligence and operational action.

1. Ask

The manager can ask:

"What inventory needs my attention?"

AptStock uses the active application context and inventory intelligence to identify relevant products.

The manager does not need to manually search the entire catalog before starting the conversation.

2. Understand

The manager can continue naturally:

"Why does that product need attention?"

"How much should I reorder?"

"What is the current stock?"

"Which product should I handle first?"

The purpose is to turn inventory intelligence into a conversational decision interface.

3. Explain

A recommendation should not be treated as an unexplained number.

Depending on the available store data, AptStock can use signals such as:

Historical sales
Demand patterns
Forecasts
Inventory information
Safety-stock logic
Lead-time information
Inventory risk
Replenishment requirements

The voice layer makes those decisions accessible conversationally.

The design principle is:

BUSINESS DATA
      ↓
APTSTOCK LOGIC
      ↓
STRUCTURED RESULT
      ↓
VOICE EXPLANATION

The assistant should explain the decision from available application context rather than inventing business facts.

4. Prepare a Reorder — Don't Blindly Execute

AptStock separates reorder preparation from an external supplier purchase.

For example:

Manager: Prepare a reorder for Heritage Curd Cup.

AptStock prepares a reorder draft.

Conceptually:

VOICE INTENT
     ↓
VALIDATION
     ↓
REORDER DRAFT
     ↓
PENDING STATE

The system does not claim that a supplier order was placed when the application has only prepared a draft.

This distinction is central to the product's operational-control model.

5. Correct the Decision

Real conversations change.

For example:

Manager:
Prepare a reorder for Heritage Curd Cup.

AptStock:
I've prepared the reorder draft.

Manager:
Change the quantity to 200.

AptStock:
The reorder quantity has been updated.

The important behavior is that the changed quantity becomes a new state of the draft.

DRAFT
  ↓
CHANGE
  ↓
UPDATED DRAFT
  ↓
NEW CONFIRMATION

An earlier conversational approval should not silently become approval for a materially changed action.

6. Cancel

The manager can cancel a pending reorder draft.

PENDING REORDER
      ↓
    CANCEL
      ↓
  CANCELLED

The application distinguishes cancellation of a pending draft from reversal of an already-completed external transaction.

That boundary matters when voice is connected to operational actions.

7. Human Assistance

Automation should not pretend to be a human.

A manager can request assistance:

"I need to speak with someone."

AptStock can create a persisted human-assistance request for follow-up.

The system does not claim that a live telephone transfer occurred unless an actual telephony transfer exists.

Multi-SKU Intelligence

AptStock is designed around multi-SKU retail rather than a single-product demonstration.

The operational challenge can look like:

SKU 1
SKU 2
SKU 3
SKU 4
...
SKU N

The manager cannot realistically treat every SKU as equally urgent.

AptStock therefore focuses the workflow on prioritization:

ALL STORE DATA
       ↓
INVENTORY INTELLIGENCE
       ↓
PRIORITIZED PRODUCTS
       ↓
MANAGER ASKS
       ↓
VOICE REASONING
       ↓
CONTROLLED ACTION

The objective is to focus human attention where the inventory system identifies meaningful risk or replenishment needs.

Why This Is More Than a Voice Wrapper

A generic voice assistant can follow a conversation.

AptStock connects conversation to a domain-specific operational system.

Generic voice assistant
SPEECH
   ↓
AI
   ↓
ANSWER
AptStock
SPEECH
   ↓
ASSEMBLYAI VOICE AGENT
   ↓
STORE CONTEXT
   ↓
INVENTORY INTELLIGENCE
   ↓
FORECAST / RISK / PRIORITY
   ↓
EXPLANATION
   ↓
REORDER DRAFT
   ↓
CHANGE / CANCEL / ESCALATE
   ↓
STATE VERIFICATION

The distinction is important:

The AI conversation does not own the inventory state.
The AptStock application owns the inventory state.

AssemblyAI Integration

AptStock uses AssemblyAI's Voice Agent API as the real-time conversational layer.

The integration connects the voice experience to AptStock's inventory tools and application context.

MICROPHONE
    ↓
ASSEMBLYAI VOICE AGENT
    ↓
TOOL CALL
    ↓
APTSTOCK BACKEND
    ↓
STRUCTURED TOOL RESULT
    ↓
ASSEMBLYAI AGENT
    ↓
SPOKEN RESPONSE

The Voice Agent API provides the real-time conversational infrastructure, including speech recognition, turn detection, voice generation, interruption handling, and JSON-schema-based tool calling.

AptStock adds the domain-specific layer:

retail inventory intelligence + prioritization + controlled operational actions.

Voice Tools

The demonstrated workflow uses domain-specific tools including:

get_inventory_alerts

Retrieves inventory context and relevant priority information for the active store.

prepare_reorder

Creates a controlled reorder draft using the requested SKU and quantity after application validation.

cancel_reorder

Cancels a pending reorder draft.

transfer_to_human

Creates a persisted human-assistance request when the manager needs human support.

These tools connect the conversational interface to application state instead of returning purely conversational answers.

Controlled Action Architecture

AptStock follows a simple boundary:

AI INTERPRETS
      ↓
APPLICATION VALIDATES
      ↓
BACKEND OWNS STATE
      ↓
ACTION IS CONTROLLED
      ↓
STATE IS VERIFIED

This separation is intentional.

The language model should not be treated as the authoritative inventory database.

The application remains responsible for inventory state and operational action state.

Interruption and Barge-In

Natural conversation requires the manager to be able to interrupt.

AptStock's client-side voice workflow handles interruption by stopping current playback and preventing stale asynchronous audio or interrupted work from continuing into the new conversational turn.

Conceptually:

AGENT SPEAKING
      ↓
MANAGER INTERRUPTS
      ↓
STOP CURRENT PLAYBACK
      ↓
INVALIDATE STALE RESPONSE
      ↓
RESUME LISTENING
      ↓
PROCESS NEW TURN

AssemblyAI's Voice Agent API explicitly supports interruption-aware turn handling; its documentation describes interrupted replies and the need for clients to flush playback and discard pending tool results for interrupted turns.

This matters because operational voice interaction should respect the manager's new instruction rather than allowing stale conversational state to continue.

The State Machine

AptStock's reorder workflow can be understood as a controlled state transition:

                  ┌──────────────┐
                  │    READY     │
                  └──────┬───────┘
                         │
                         ▼
                ┌──────────────────┐
                │ REORDER PREPARED │
                └────────┬─────────┘
                         │
                 ┌───────┴────────┐
                 │                │
                 ▼                ▼
            CHANGE             CANCEL
                 │                │
                 ▼                ▼
        UPDATED DRAFT         CANCELLED
                 │
                 ▼
       NEW CONFIRMATION

This is why AptStock is not simply:

"Ask an AI about your inventory."

It is:

"Use voice to operate a controlled inventory decision workflow."

End-to-End Example
Manager:
What inventory needs my attention?

AptStock:
Heritage Curd Cup is one of the products requiring attention.

Manager:
Why?

AptStock:
It is showing inventory risk based on the available
sales and replenishment signals.

Manager:
How much should I reorder?

AptStock:
The current AptStock recommendation is [live recommendation].

Manager:
Prepare the reorder.

AptStock:
I've prepared a reorder draft.

Manager:
Change the quantity to 200.

AptStock:
The reorder quantity has been updated to 200 units.

Manager:
Actually, cancel it.

AptStock:
The pending reorder has been cancelled.

Manager:
I need help from someone.

AptStock:
I've submitted a request for an AptStock team member to assist you.

The actual quantities and inventory values come from the application's live state.

Business Value

The product is aimed at a concrete operational problem:

How can a store operator quickly identify which inventory decisions deserve attention and act on them without manually searching through a large SKU catalog?

AptStock connects:

WHAT IS HAPPENING?
        ↓
WHY?
        ↓
WHAT SHOULD I DO?
        ↓
HOW MUCH?
        ↓
PREPARE
        ↓
CHANGE OR CANCEL

Potential operational benefits include:

Faster identification of inventory risks
Less manual SKU-by-SKU inspection
Faster access to replenishment recommendations
More accessible inventory intelligence
A controlled path from recommendation to reorder preparation
Conversational access to complex inventory workflows

The product is not positioned as an autonomous purchasing system.

The manager remains in control of the operational decision.

What Makes AptStock Distinct

The central idea is:

Predictive replenishment operated conversationally.

AptStock combines two layers that are usually experienced separately:

PREDICTIVE INVENTORY INTELLIGENCE
              +
REAL-TIME CONVERSATIONAL OPERATION

The complete loop is:

REAL STORE DATA
      ↓
DEMAND FORECAST
      ↓
INVENTORY OPTIMIZATION
      ↓
MULTI-SKU PRIORITY
      ↓
VOICE REASONING
      ↓
CONTROLLED REORDER
      ↓
CHANGE / CANCEL
      ↓
INTERRUPTION SAFETY
      ↓
STATE VERIFICATION

That loop is the product story.

Technology Stack
Voice
AssemblyAI Voice Agent API
Real-time WebSocket communication
Streaming microphone audio
Voice agent tool calling
Turn detection
Interruption handling
Frontend
React
Browser Web Audio APIs
WebSocket client
Voice state management
Inventory / forecasting dashboard
Backend
FastAPI
Python
MongoDB
Pandas
NumPy
Forecasting and inventory-intelligence services
Architecture
                         ┌──────────────────────┐
                         │       MANAGER        │
                         │     Voice Input      │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │      ASSEMBLYAI      │
                         │    VOICE AGENT API   │
                         │                      │
                         │ Voice / Turns /      │
                         │ Tool Calling         │
                         └──────────┬───────────┘
                                    │
                               Tool Calls
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │   APTSTOCK ACTION    │
                         │        LAYER         │
                         └──────────┬───────────┘
                                    │
              ┌─────────────────────┼─────────────────────┐
              │                     │                     │
              ▼                     ▼                     ▼
       Inventory Query       Reorder Draft        Human Assistance
              │                     │                     │
              ▼                     ▼                     ▼
       AptStock Engine       Backend State           MongoDB
              │                     │
              └─────────────┬───────┘
                            ▼
                    Structured Result
                            │
                            ▼
                     AssemblyAI Agent
                            │
                            ▼
                     Spoken Response
Application Workflow
1. Store sales data enters AptStock
                 ↓
2. Data is normalized and validated
                 ↓
3. Demand and inventory intelligence is generated
                 ↓
4. Products requiring attention are prioritized
                 ↓
5. Manager opens the voice interface
                 ↓
6. Manager asks about inventory
                 ↓
7. AssemblyAI handles the real-time conversation
                 ↓
8. AptStock tools provide application data
                 ↓
9. Manager asks why / how much / what next
                 ↓
10. AptStock prepares a controlled reorder draft
                 ↓
11. Manager can change or cancel the draft
                 ↓
12. Human assistance can be requested when needed
Reliability Philosophy

AptStock follows one operational principle:

AI can interpret the conversation, but the application owns the business state.

Therefore:

AI PROPOSES
     ↓
APPLICATION VALIDATES
     ↓
BACKEND OWNS STATE
     ↓
CONTROLLED ACTION
     ↓
STATE VERIFICATION

This separation is especially important for:

SKU identity
Store context
Quantities
Reorder drafts
Cancellation
Human-assistance requests
Why This Matters for Retail

The long-term vision is not to replace a retailer's existing dashboard.

The dashboard remains valuable for exploration and detailed analysis.

The voice layer addresses a different moment:

When the manager needs to know what matters and decide what to do next.

Instead of requiring the manager to navigate through every screen, AptStock provides a conversational path into the same underlying inventory intelligence.

MANY PRODUCTS
      ↓
INVENTORY INTELLIGENCE
      ↓
PRIORITIZED ATTENTION
      ↓
VOICE ACCESS
      ↓
CONTROLLED DECISION
Hackathon Focus

AptStock was built for the AssemblyAI Voice Agent Hackathon around four ideas:

Application of Technology

AssemblyAI is integrated into the live conversational workflow with domain-specific inventory tools rather than being used only for transcription. The architecture connects voice turns to real AptStock application state and controlled actions.

Presentation

The product is demonstrated as one continuous workflow:

DATA
 ↓
INTELLIGENCE
 ↓
PRIORITY
 ↓
VOICE
 ↓
ACTION
 ↓
CHANGE / CANCEL
 ↓
VERIFICATION
Business Value

The target user is a multi-SKU store operator who needs to decide which inventory issue deserves attention next.

Originality

The core concept combines:

predictive replenishment + multi-SKU prioritization + conversational operation + controlled action.

The result is not simply a voice assistant answering inventory questions.

It is a conversational interface to an inventory decision workflow.

What AptStock Is — and Is Not
AptStock is:
A voice-native inventory decision copilot
A demand forecasting and inventory intelligence layer
A multi-SKU prioritization system
A conversational interface to inventory workflows
A controlled reorder-draft workflow
AptStock is not:
A generic chatbot
A voice-only demonstration
A replacement for a retailer's entire ERP
An autonomous purchasing system
A source of invented inventory facts
A system that claims a supplier order was placed when only a draft was created

The distinction is intentional.

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
Key Inventory Endpoints
GET
/api/inventory-alerts

POST
/api/inventory/prepare-reorder

POST
/api/inventory/cancel-reorder

POST
/api/inventory/request-human-assistance

These endpoints form the bridge between the conversational layer and the inventory action workflow.

Production / Deployment

AptStock is deployed as a working application with a live frontend, backend, database, and AssemblyAI-powered voice workflow.

The repository is provided so the implementation and architecture can be inspected rather than treating the project as a black-box presentation.

The Core Loop
                         ┌─────────────┐
                         │     ASK     │
                         └──────┬──────┘
                                ↓
                         ┌─────────────┐
                         │ UNDERSTAND  │
                         └──────┬──────┘
                                ↓
                         ┌─────────────┐
                         │   EXPLAIN   │
                         └──────┬──────┘
                                ↓
                         ┌─────────────┐
                         │  RECOMMEND  │
                         └──────┬──────┘
                                ↓
                         ┌─────────────┐
                         │   PREPARE   │
                         └──────┬──────┘
                                ↓
                         ┌─────────────┐
                         │  CONFIRM    │
                         └──────┬──────┘
                                ↓
                       ┌────────┴────────┐
                       ↓                 ↓
                    CHANGE            CANCEL
                       ↓                 ↓
                 NEW DRAFT          CANCELLED
                       ↓
               NEW CONFIRMATION
Final Idea

AptStock starts with a retailer's existing data.

It turns that data into inventory intelligence.

It prioritizes what deserves attention.

AssemblyAI makes that intelligence conversational.

The application then provides a controlled path from:

identify → explain → recommend → prepare → change → cancel → verify

The goal is not to make voice sound impressive.

The goal is to make the next inventory decision:

easier to understand, faster to reach, and safer to control.

Built With

AssemblyAI Voice Agent API · React · FastAPI · Python · MongoDB · Pandas · NumPy

AptStock AI
