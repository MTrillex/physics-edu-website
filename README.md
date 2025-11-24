# Interactive Physics Education Platform

A comprehensive web-based learning platform designed to help IGCSE physics students understand the fundamental physics concepts through interactive simulations and engaging educational content. Built with accuracy and educational value at its core, this platform transforms abstract physics principles into tangible, explorable experiences.

## Overview

This project addresses a critical gap in physics education by providing students with hands-on, visual learning tools that complement traditional textbook methods. Rather than simply reading about physics concepts, students can manipulate variables, observe real-time changes, and develop intuitive understanding through experimentation. The platform covers the complete IGCSE physics curriculum across six major domains: mechanics, thermal physics, waves, electricity and magnetism, nuclear physics, and space physics.

## Key Features

### Interactive Simulation Suite

The platform features 16 purpose-built physics simulations, each implementing accurate physical models through sophisticated algorithms:

**Mechanics Simulations**
- **Motion Simulator**: Demonstrates uniform and accelerated motion with real-time visualization of position, velocity, and acceleration. Features collision detection and boundary handling.
- **Graph Generator**: Dynamically plots position-time, velocity-time, and acceleration-time graphs based on user-defined parameters, with LaTeX-formatted equations.
- **Projectile Motion**: Simulates realistic projectile trajectories with wall collision detection, allowing students to experiment with launch angles and velocities.
- **Spring Dynamics**: Models Hooke's law with adjustable spring constants and masses, displaying force vectors and energy graphs in real-time.
- **Kinetic-Potential Energy Converter**: Visualizes energy transformation between kinetic and potential forms, with optional friction to demonstrate energy dissipation.
- **Momentum Conservation**: Demonstrates elastic collisions between irregular polygons with accurate 2D momentum calculations and vector visualization.
- **Newton's Cradle**: Physics-accurate pendulum system using the Pymunk physics engine, demonstrating conservation of momentum and energy.
- **Orbital Mechanics**: Simulates gravitational interactions between celestial bodies with configurable masses and velocities, showing stable and unstable orbits.

**Thermodynamics Simulations**
- **Brownian Motion**: Particle-based simulation demonstrating random molecular movement, with selectable particles to track individual trajectories and velocity vectors.
- **Kinetic Particle Model**: Interactive visualization of matter states (solid, liquid, gas) with temperature control, particle addition, and real-time kinetic energy calculations.
- **Heat Transfer Demonstration**: Visual representation of thermal energy transfer methods with adjustable parameters.

**Wave Physics Simulations**
- **Sound Wave Propagation**: Longitudinal wave simulator showing compression and rarefaction with adjustable amplitude, frequency, and wavelength. Displays wave equations in LaTeX format.
- **Transverse Wave Motion**: Demonstrates transverse wave properties with real-time equation display, phase tracking, and adjustable wave parameters.

**Electromagnetism Simulations**
- **Electric Current Flow**: Visualizes electron drift and current measurement in conductors, with interactive particle systems demonstrating charge movement.
- **Electrostatics Simulator**: Models electrostatic forces between multiple charged particles with Coulomb's law calculations, supporting both random and organized charge distributions.
- **DC and AC Current**: Comparative demonstration of direct and alternating current behavior with real-time current measurements.
- **Electromagnetic Effects**: Interactive demonstrations of magnetic field interactions and electromagnetic induction principles.

### Content Management System

The platform includes a complete content management system designed for educational institutions:

- **User Authentication**: Secure role-based access control with three user types (student, teacher, admin)
- **Note System**: Comprehensive note-taking and organization system mapped to IGCSE syllabus sections (Topics 1.1 through 6.2)
- **Topic Organization**: Structured content delivery following the official Cambridge IGCSE Physics curriculum (0625/0972)
- **Admin Dashboard**: Content creation and editing interface for administrators
- **Teacher Tools**: Note editing capabilities for educators to customize content for their students

### Technical Architecture

**Backend Framework**
- Flask web framework with blueprint architecture for modular organization
- SQLAlchemy ORM for database management with Flask-Migrate for schema versioning
- Flask-Login for session management and user authentication
- RESTful API design for simulation state management

**Physics Engine**
- Custom simulation framework with abstract base classes ensuring consistent interfaces
- Pymunk 2D physics engine integration for rigid body dynamics
- Thread-safe simulation updates with mutex locks
- Real-time state synchronization between backend and frontend

**Frontend Technologies**
- Vanilla JavaScript for simulation rendering and interaction
- Matter.js for additional physics visualizations
- KaTeX for mathematical equation rendering
- Plotly.js for dynamic graph generation
- Vue.js components for reactive UI elements

**Database Schema**
- User model with role-based permissions (student, teacher, admin)
- Note model with topic organization and relationship mapping
- SQLite database for development with easy migration to production databases

## Installation and Setup

### Prerequisites

- Python 3.8 or higher
- pip package manager
- Virtual environment support (venv)

### Installation Steps

1. Clone the repository:
```bash
git clone https://github.com/MTrillex/physics-education-website.git
cd physics-education-website
```

2. Create and activate a virtual environment:
```bash
python3 -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Initialize the database:
```bash
flask db upgrade
```

5. Run the application:
```bash
python main.py
```

The application will be available at `http://localhost:5000`

### Default Credentials

The system automatically creates a default admin account on first run:
- **Username**: admin
- **Email**: adminofwebsite@gmail.com
- **Password**: adminowner

It is strongly recommended to change these credentials immediately after first login.

## Project Structure

```
physics-education-website/
├── main.py                      # Application entry point
├── requirements.txt             # Python dependencies
├── website/
│   ├── __init__.py             # Flask app factory and configuration
│   ├── models.py               # Database models (User, Note)
│   ├── auth.py                 # Authentication routes and user management
│   ├── views.py                # Main application views
│   ├── simulations/            # Physics simulation modules
│   │   ├── base.py            # Abstract simulation class
│   │   ├── manager.py         # Simulation registry and lifecycle
│   │   ├── routes.py          # Simulation API endpoints
│   │   ├── mechanics.py       # Mechanics simulations
│   │   ├── thermodynamics.py  # Thermal physics simulations
│   │   ├── waves.py           # Wave simulations
│   │   └── electromagnetism.py # EM simulations
│   ├── static/
│   │   ├── style.css          # Global styling
│   │   ├── script.js          # Client-side interactions
│   │   ├── lib/               # Third-party libraries
│   │   └── sims/              # Simulation HTML interfaces
│   └── templates/
│       ├── base.html          # Base template with navigation
│       ├── home.html          # Landing page
│       ├── note.html          # Note viewing interface
│       ├── sim.html           # Simulation container
│       └── login.html         # Authentication pages
└── migrations/                 # Database migration scripts
```

## Curriculum Coverage

The platform comprehensively covers all sections of the IGCSE Physics syllabus:

**Section 1: General Physics**
- Physical quantities and measurement (1.1)
- Motion (1.2)
- Mass and weight (1.3)
- Density (1.4)
- Forces (1.5)
- Momentum (1.6)
- Energy, work and power (1.7)
- Pressure (1.8)

**Section 2: Thermal Physics**
- Kinetic particle model of matter (2.1)
- Thermal properties and temperature (2.2)
- Transfer of thermal energy (2.3)

**Section 3: Properties of Waves**
- General properties of waves (3.1)
- Light (3.2)
- Electromagnetic spectrum (3.3)
- Sound (3.4)

**Section 4: Electricity and Magnetism**
- Simple phenomena of magnetism (4.1)
- Electrical quantities (4.2)
- Electric circuits (4.3)
- Electrical safety (4.4)
- Electromagnetic effects (4.5)

**Section 5: Nuclear Physics**
- The nuclear model of the atom (5.1)
- Radioactivity (5.2)

**Section 6: Space Physics**
- Earth and the Solar System (6.1)
- Stars and the Universe (6.2)

## API Documentation

### Simulation Endpoints

All simulations follow a consistent REST API pattern:

**Initialize Simulation**
```
GET /api/{simulation}/init
Returns: Initial simulation state as JSON
```

**Update Simulation**
```
POST /api/{simulation}/update
Body: { action: string, parameters: object }
Returns: Updated simulation state as JSON
```

**Common Actions**
- `set_pause`: Pause/resume simulation
- `reset`: Reset to initial conditions
- Simulation-specific actions (e.g., `fire` for projectile, `set_temperature` for particle model)

### Note Endpoints

**View Note**
```
GET /note/{topic_directory}
Returns: Note content page
```

**Get Note Data**
```
GET /api/note/{topic_directory}
Returns: { title: string, data: string, topic_directory: string }
```

**Create Note** (Admin only)
```
POST /create-note
Body: { noteTitle: string, topicDirectory: string, noteContent: string }
```

## Educational Impact

This platform serves multiple educational purposes:

1. **Conceptual Understanding**: Visual representations help students grasp abstract concepts that are difficult to understand through text alone.

2. **Active Learning**: Interactive simulations encourage experimentation and discovery-based learning, leading to deeper understanding.

3. **Immediate Feedback**: Real-time visualization allows students to instantly see the effects of changing variables, reinforcing cause-and-effect relationships.

4. **Curriculum Alignment**: Direct mapping to IGCSE syllabus topics ensures relevance to examination preparation.

5. **Accessibility**: Web-based platform accessible from any desktop device with a browser, removing barriers to quality physics education.

## Technical Highlights

- **Thread-Safe Simulations**: Mutex locks ensure simulation state consistency during concurrent access
- **Modular Architecture**: Blueprint-based organization allows easy addition of new simulations
- **Physics Accuracy**: Implementations use established physics equations and numerical methods
- **Performance Optimization**: Efficient update loops with configurable time steps for smooth rendering

## Future Development

Potential enhancements under consideration:

- Mobile-optimized simulation interfaces
- Student progress tracking and analytics
- Collaborative features for classroom use
- Additional simulations for advanced topics
- Multi-language support
- Integration with learning management systems (LMS)
- Quiz and assessment modules
- 3D simulation capabilities using WebGL

## License

This project is educational software designed for academic use.

## Acknowledgments

Built with a focus on educational quality and scientific accuracy, this platform represents the intersection of physics education and modern web technology. Special attention has been paid to ensuring all simulations reflect real physical principles while remaining accessible to IGCSE-level students.

## Contact

For questions, suggestions, or collaboration inquiries, please contact me at davidtrillex@gmail.com.

---

**Author**: Avi Dabral  
**Purpose**: Educational tool for IGCSE Physics students  
**Status**: Active development
