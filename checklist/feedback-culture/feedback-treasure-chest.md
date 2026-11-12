# Feedback „Treasure Chest”


# LI Post

🏆 Transform Your Feedback into Treasure 💎
Ever feel like valuable feedback slips through your fingers? Time to turn those insights into gems! 💡

Treat any feedback you get as a Gem 💎 and build yourself a Feedback Treasure Chest! Here's how it works:

For each piece of feedback, track: 
✨ The feedback itself 
👤 Who gave it and when 
📝 The context 
✅ Action taken 
🎯 Outcomes & learnings

Make it fun by: 
💎 Assigning different gem types (rubies for technical feedback, emeralds for leadership insights) 
📊 Tracking your action rate 
🔍 Identifying patterns in your growth journey

Why this matters:
* Perfect for performance reviews
* Keeps imposter syndrome in check
* Shows your growth trajectory
* Makes feedback actionable

You can use any tool you feel comfortable with for this - Google Sheets, Notion etc. 

Pro tip: Keep it simple! Start with these basic dimensions and adapt as needed. The goal is to make feedback tracking a habit, not a chore.

🎮 Bonus: Gamify your growth! Set milestone rewards for yourself as you collect and action feedback gems.

What's your favourite way to track professional growth? Share in the comments!

---

![](feedback-treasure-chest.png)

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
      padding: 20px;
      background: #f5f5f5;
    }

    .treasure-chest {
      max-width: 800px;
      margin: 0 auto;
      background: linear-gradient(to right, #faf5ff, #eff6ff);
      border-radius: 12px;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    }

    .chest-header {
      padding: 20px;
      border-bottom: 1px solid #e5e7eb;
    }

    .chest-title {
      display: flex;
      align-items: center;
      gap: 10px;
      font-size: 1.5rem;
      font-weight: bold;
      color: #1a1a1a;
    }

    .chest-content {
      padding: 20px;
    }

    .progress-section {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 20px;
      padding: 15px;
      background: white;
      border-radius: 8px;
    }

    .progress-title {
      display: flex;
      align-items: center;
      gap: 8px;
      font-weight: 600;
    }

    .progress-stats {
      text-align: right;
    }

    .progress-percentage {
      font-size: 1.5rem;
      font-weight: bold;
      color: #4f46e5;
    }

    .progress-detail {
      font-size: 0.875rem;
      color: #666;
    }

    .feedback-list {
      display: grid;
      gap: 15px;
    }

    .feedback-card {
      background: white;
      border-radius: 8px;
      padding: 15px;
      box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
    }

    .feedback-content {
      display: flex;
      gap: 12px;
    }

    .gem-icon {
      width: 24px;
      height: 24px;
    }

    .feedback-text {
      flex: 1;
    }

    .feedback-message {
      font-weight: 500;
      margin-bottom: 8px;
    }

    .feedback-meta {
      font-size: 0.875rem;
      color: #666;
    }

    .feedback-outcome {
      margin-top: 8px;
      color: #059669;
    }

    .add-feedback {
      display: flex;
      align-items: center;
      gap: 8px;
      margin-top: 20px;
      padding: 8px;
      border: none;
      background: none;
      color: #4f46e5;
      font-size: 0.875rem;
      cursor: pointer;
    }

    .add-feedback:hover {
      color: #4338ca;
    }

    /* Icons */
    .icon {
      display: inline-block;
      width: 20px;
      height: 20px;
    }
  </style>
</head>
<body>
  <div class="treasure-chest">
    <header class="chest-header">
      <h1 class="chest-title">
        <span class="icon">👑</span>
        Feedback Treasure Chest
      </h1>
    </header>

    <main class="chest-content">
      <div class="progress-section">
        <div class="progress-title">
          <span class="icon">🏆</span>
          Progress
        </div>
        <div class="progress-stats">
          <div class="progress-percentage">75%</div>
          <div class="progress-detail">3 of 4 actioned</div>
        </div>
      </div>

      <div class="feedback-list" id="feedbackList">
        <!-- Feedback items will be inserted here via JavaScript -->
      </div>

      <button class="add-feedback">
        <span class="icon">➕</span>
        Add New Feedback Gem
      </button>
    </main>
  </div>

  <script>
    class FeedbackTracker {
      constructor() {
        this.feedbacks = [
          {
            id: 1,
            feedback: "Great leadership in the recent project launch",
            source: "Sarah (Team Lead)",
            date: "2024-03-15",
            context: "Project Alpha completion",
            actioned: true,
            outcome: "Implemented similar leadership approach in Project Beta",
            gemType: "diamond"
          },
          {
            id: 2,
            feedback: "Could improve technical documentation",
            source: "John (Senior Dev)",
            date: "2024-03-20",
            context: "Code review session",
            actioned: true,
            outcome: "Created documentation template, team productivity increased",
            gemType: "ruby"
          }
        ];
        
        this.init();
      }

      init() {
        this.renderFeedbacks();
        this.attachEventListeners();
      }

      getGemIcon(type) {
        const icons = {
          diamond: "💎",
          ruby: "❤️",
          emerald: "💚"
        };
        return icons[type] || "💎";
      }

      getProgressStats() {
        const total = this.feedbacks.length;
        const actioned = this.feedbacks.filter(f => f.actioned).length;
        return {
          percentage: Math.round((actioned / total) * 100),
          actioned,
          total
        };
      }

      renderFeedbacks() {
        const container = document.getElementById('feedbackList');
        container.innerHTML = this.feedbacks.map(feedback => `
          <div class="feedback-card" data-id="${feedback.id}">
            <div class="feedback-content">
              <span class="gem-icon">${this.getGemIcon(feedback.gemType)}</span>
              <div class="feedback-text">
                <p class="feedback-message">${feedback.feedback}</p>
                <div class="feedback-meta">
                  <p>From: ${feedback.source} on ${feedback.date}</p>
                  <p>Context: ${feedback.context}</p>
                  ${feedback.actioned ? `
                    <p class="feedback-outcome">✓ Actioned: ${feedback.outcome}</p>
                  ` : ''}
                </div>
              </div>
            </div>
          </div>
        `).join('');

        // Update progress
        const stats = this.getProgressStats();
        document.querySelector('.progress-percentage').textContent = `${stats.percentage}%`;
        document.querySelector('.progress-detail').textContent = 
          `${stats.actioned} of ${stats.total} actioned`;
      }

      attachEventListeners() {
        document.querySelector('.add-feedback').addEventListener('click', () => {
          // In a real application, this would open a modal or form
          alert('Add feedback form would open here');
        });
      }
    }

    // Initialize the tracker when the page loads
    document.addEventListener('DOMContentLoaded', () => {
      new FeedbackTracker();
    });
  </script>
</body>
</html>
```
