# Mountain Tours - C4 Architecture Diagrams

Interactive C4 architecture diagrams for the Mountain Tours system, built with [LikeC4](https://likec4.dev).

## Files

- `model.c4` - Defines the architecture model (actors, systems, containers, components)
- `views.c4` - Defines the views/diagrams to generate from the model

## Running Locally

### Start the interactive preview server

```bash
npm run dev
```

This will start a dev server at http://localhost:3456 with:
- Interactive diagram viewer
- Hot reload on file changes
- Navigation between views
- Zoom and pan controls

### Alternative: Quick preview

```bash
npm run preview
```

Opens a preview in your default browser (no hot reload).

## Available Views

### System Level
- **System Context** - High-level view of actors and external systems
- **Container Diagram** - All services, databases, and infrastructure

### Service Components
- **IAM Service Components** - Authentication and authorization
- **Tours Service Components** - Tour management (CQRS pattern)
- **Booking Service Components** - Reservation and payment processing
- **Review Service Components** - Rating and feedback system
- **Notification Service Components** - Real-time communication

### Focused Views
- **Event-Driven Communication** - RabbitMQ message flow
- **Real-Time Features** - SignalR and live tracking
- **Payment Flow** - Stripe integration

### Actor Journeys
- **User Journey** - Search, book, review flow
- **Guide Journey** - Availability and live location
- **Operator Journey** - Tour creation and management

## Exporting Diagrams

### Export all views as PNG

```bash
npm run export
```

Images will be saved to `./exports/`

### Build static website

```bash
npm run build
```

Generates a static site in `./dist/` that you can deploy anywhere.

## Editing

1. Edit `model.c4` to add/modify elements and relationships
2. Edit `views.c4` to change what's shown in diagrams
3. Save - changes appear instantly in the dev server

## LikeC4 Features

- 🎨 Automatic layout and styling
- 🔄 Live reload during development
- 📱 Responsive diagrams
- 🖱️ Interactive navigation
- 📤 Export to PNG, SVG, JSON
- 🌐 Deploy as static website
- 🔗 Deep linking to specific views

## Documentation

- [LikeC4 Documentation](https://likec4.dev/docs/)
- [Tutorial](https://likec4.dev/tutorial/)
- [Examples](https://likec4.dev/examples/)
