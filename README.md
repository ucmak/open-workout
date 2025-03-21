# Movio Workout Recipe Schema

This repository contains the specification for the Movio recipe exchange format, a standardized JSON format for fitness workout recipes.

## Format Specification (v1.0.0)

The Movio recipe format uses a JSON structure to store workout recipes, including exercises and their parameters.

## Purpose

The Movio Recipe Schema provides a standardized format for exchanging workout recipes between fitness applications. This format allows:

- Sharing workouts between Movio users
- Backing up your favorite workout templates
- Publishing workout routines for others to follow
- Importing routines from trainers and fitness professionals

## Implementation Guidance

When implementing this schema in your own application:

1. **Validate schema version** - Check the `schemaVersion` field to ensure compatibility
2. **Handle missing optional fields** - Use sensible defaults for any missing optional fields
3. **Preserve unknown fields** - When re-exporting, preserve any fields not defined in the schema
4. **Error handling** - Provide clear error messages when importing invalid data

## Extensions

The schema allows for future extensions through additional fields. Applications should ignore fields they don't recognize rather than rejecting the file.

## Community

We welcome contributions to the Movio Recipe Schema. Please submit pull requests or issues on this repository to suggest improvements.

### Recipe Fields

| Field | Type | Description | Required |
|-------|------|-------------|----------|
| schemaVersion | String | Version of the Movio recipe schema | Yes |
| name | String | Name of the workout recipe | Yes |
| notes | String | Additional notes or description | No |
| activityName | String | Type of workout activity | No |
| videoURL | String | URL to a demonstration video | No |
| created | ISO 8601 Date | Date when recipe was created | Yes |
| exercises | Array | List of exercises in the workout | Yes |
| exportDate | ISO 8601 Date | Date when recipe was exported | Yes |
| appVersion | String | Version of the app that exported the recipe | Yes |

### Exercise Fields

| Field | Type | Description | Required |
|-------|------|-------------|----------|
| name | String | Name of the exercise | Yes |
| sets | Integer | Number of sets | Yes |
| reps | Integer | Number of repetitions per set | Yes |
| weight | Number | Weight in kg (null if not applicable) | No |
| time | Integer | Time in seconds (0 if not applicable) | Yes |
| distance | Number | Distance in km (null if not applicable) | No |
| instructions | String | Additional instructions for the exercise | No |

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


