🧮 Data Requirements
Knowledge Base · Sources + Quantity
Sources:

• The Listing House Rules (PDF/Text)

• The Damage Claim Form (JSON)

• The Last 48 hours of Guest/Host Messaging History

Quantity: Limit message ingestion to the specific booking ID where the dispute occurred to prevent cross-contamination of user history.

Sync Frequency & Refresh
Real-time trigger: The knowledge base must refresh its index instantly upon submission of a new damage claim or new message in the dispute thread.

Requirement: To ensure legal accuracy, the “House Rules” segment must be a live pull from the production database at the time of claim filing.

📐 Model Requirements
Retrieval Strategy · Hybrid Approach
Justification: We need the AI to find specific details (exact line in the house rules, specific item in a photo caption) while also understanding broader context of the conversation (whether a guest is being aggressive or genuinely confused).

💰 AI Costs & Latency
Context Requirement · Top-K = 8
Limit: Top 8 retrieval segments.

Justification: Tell the AI to only look at the 8 most relevant snippets from the rules and chat logs. Too much → slow, expensive, lost focus on key facts. This keeps response < 3s so the user doesn’t feel the app is stuck.

🤝 AI User Experience
Grounded Trust Requirement
Verification: The AI cannot just give a Yes/No answer. It must show the receipts, every decision points directly to the specific rule or photo it used.

Fail-safe: If the AI can’t find a clear reason to charge a guest, it must stop and say “I don’t have enough evidence to decide,” and pass the case to a human. We prefer cautious over guessing.
