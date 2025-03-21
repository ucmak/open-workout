# Movio Recipe Schema

This repository contains the specification for the Movio recipe exchange format, a standardized JSON format for fitness workout recipes.

## Format Specification (v1.0.0)

The Movio recipe format uses a JSON structure to store workout recipes, including exercises and their parameters.

### Recipe Structure

```json
{
  "schemaVersion": "1.0.0",
  "name": "Full Body Strength",
  "notes": "A comprehensive workout targeting all major muscle groups.",
  "activityName": "Strength Training",
  "videoURL": "https://example.com/workout-video",
  "created": "2023-08-15T10:30:00Z",
  "exercises": [
    {
      "name": "Push-ups",
      "sets": 3,
      "reps": 15,
      "weight": null,
      "time": 0,
      "distance": null,
      "instructions": "Keep your core tight throughout the movement"
    },
    {
      "name": "Squats",
      "sets": 4,
      "reps": 12,
      "weight": 30.0,
      "time": 0,
      "distance": null,
      "instructions": null
    },
    {
      "name": "Plank",
      "sets": 1,
      "reps": 1,
      "weight": null,
      "time": 60,
      "distance": null,
      "instructions": "Hold position for full time"
    }
  ],
  "exportDate": "2023-08-20T15:45:30Z",
  "appVersion": "1.0"
}
