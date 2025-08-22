---
layout: page
title: San Francisco Traffic Impact Simulation
subtitle: IEOR 174 Systems Simulation | UC Berkeley
---

# Simulating Traffic Impacts in San Francisco
**UC Berkeley IEOR 174 Systems Simulation | Academic Capstone Project**

<div class="pdf-viewer">
  <h3>Interactive Presentation Slides</h3>
  <div id="pdf-container" style="width: 100%; height: 700px; border: 1px solid #ccc; margin: 20px 0;">
    <iframe 
      src="https://mozilla.github.io/pdf.js/web/viewer.html?file=../assets/files/IEOR_174_Project.pdf"
      width="100%" 
      height="100%" 
      style="border: none;">
    </iframe>
  </div>
  <div style="text-align: center; margin-top: 10px;">
    <a href="assets/files/IEOR_174_Project.pdf" download 
       style="margin-right: 15px; padding: 8px 16px; background-color: #28a745; color: white; text-decoration: none; border-radius: 4px;">
      ⬇️ Download PDF
    </a>
    <a href="assets/files/IEOR_174_Project.pdf" target="_blank"
       style="padding: 8px 16px; background-color: #17a2b8; color: white; text-decoration: none; border-radius: 4px;">
      🔗 Open in New Tab
    </a>
  </div>
</div>


## Project Overview

This project investigated the potential traffic impacts of San Francisco's Proposition K, which proposed closing a significant portion of the Great Highway to create a public promenade. Using MatSim, an open-source traffic simulation platform, I developed a comprehensive model of San Francisco's transportation network to analyze how this major infrastructure change would affect citywide traffic patterns.

As a San Francisco native with personal investment in this civic issue, I was motivated by the polarized public debate surrounding Proposition K. Proponents argued the closure would have minimal traffic impact, while opponents predicted significant bottlenecks. Rather than rely on political rhetoric, I decided to investigate the question through rigorous simulation modeling.

The project required approximately 40 hours of development time and involved learning multiple new technologies, overcoming significant technical challenges, and ultimately producing meaningful insights about urban transportation planning through quantitative analysis.

---

## Technical Architecture and Implementation

### Data Pipeline and Network Generation

The simulation began with raw OpenStreetMap (OSM) data containing comprehensive geographic and transportation infrastructure information for San Francisco. I developed custom JavaScript code to parse this complex dataset and transform it into MatSim-compatible network files, creating a digital representation of the city's entire road system.

This data transformation process required understanding both OSM data structures and MatSim network requirements, then building translation algorithms that preserved essential traffic flow characteristics while adapting to MatSim's specific format requirements. The resulting network captured the hierarchy of San Francisco's transportation infrastructure, from highways to local streets.

The network generation process established the foundation for all subsequent simulation activities, ensuring that the digital model accurately reflected real-world transportation infrastructure constraints and opportunities.

### Population Modeling and Demographics Integration

Creating realistic traffic patterns required developing a sophisticated population model based on actual San Francisco demographic data. I accessed San Francisco's open data library to obtain population statistics for each census tract, then developed code to process these datasets and create neighborhood-specific population objects with accurate demographic attributes.

The population generator I developed created synthetic residents representing 10% of San Francisco's actual population, assigning each agent realistic home and work locations based on census data distributions. This approach ensured that the simulation's traffic patterns reflected actual residential and employment distributions across the city.

Each synthetic agent received a daily activity pattern consisting of home-to-work and work-to-home trips, creating the foundation for analyzing commute-based traffic flows that would be most affected by Great Highway closure. This population modeling approach provided the behavioral foundation necessary for meaningful traffic impact analysis.

### MatSim Implementation and Optimization

The core simulation utilized MatSim's agent-based modeling capabilities to simulate individual travel decisions and route optimization. Each synthetic resident made independent routing decisions based on travel time minimization, with the system allowing 10 iterations for agents to learn and adapt their routes based on network congestion patterns.

This iterative learning process mimicked real-world driver behavior, where commuters gradually discover optimal routes through trial and experience. The simulation captured dynamic traffic patterns as agents responded to congestion by seeking alternative routes, creating realistic traffic distribution across the network.

The MatSim implementation required significant computational resources, ultimately necessitating migration to Oracle Cloud infrastructure with 16GB RAM and 16-core CPU to handle the simulation complexity and population scale required for meaningful analysis.

---

## Technical Challenges and Solutions

### Infrastructure and Computational Requirements

The simulation's computational demands quickly exceeded standard laptop capabilities, requiring learning cloud computing platforms and virtual machine management. I established an Oracle Cloud VM instance specifically configured for MatSim's memory and processing requirements, gaining experience with cloud-based computational infrastructure.

This infrastructure challenge provided valuable learning opportunities in distributed computing and resource optimization, skills directly applicable to enterprise-scale analytics projects. Managing computational resources became an integral part of the project development process.

The cloud migration process required understanding MatSim's specific computational requirements and configuring virtual environments that could support intensive simulation workloads while maintaining cost efficiency for academic project constraints.

### Software Integration and Tool Mastery

The project required learning multiple specialized software tools, including MatSim itself, Java programming for simulation development, OSM editing tools for network modification, and Git for version control and project management. Each tool presented unique learning curves and integration challenges.

MatSim documentation proved limited, with most available resources consisting of examples from professional city planning projects with significantly larger scopes and resources than available for this academic project. Debugging required developing deep understanding of MatSim's internal processes and error handling mechanisms.

Java development for MatSim required understanding object-oriented programming principles while working within MatSim's specific API constraints and conventions. This provided valuable experience with enterprise-level programming frameworks and large-scale software project management.

### Network Modification and Scenario Development

Creating the experimental scenario required learning JOSM (Java OpenStreetMap Editor) to accurately remove the Great Highway from the transportation network while maintaining network connectivity and realistic traffic flow patterns. This network editing process required understanding transportation engineering principles and network topology.

The network modification process had to preserve the realistic characteristics of San Francisco's transportation system while creating a plausible alternative scenario for comparison. This required balancing technical simulation requirements with real-world transportation planning considerations.

Ensuring that the modified network maintained MatSim compatibility while accurately representing the proposed infrastructure changes required iterative testing and refinement of the network editing approach.

---

## Results and Analysis

### Baseline Model Validation

The initial simulation successfully created realistic traffic patterns that aligned with expected San Francisco transportation characteristics. Home location distributions showed appropriate geographic spread across residential neighborhoods, while work locations concentrated in downtown areas consistent with actual employment patterns.

Traffic volume visualizations demonstrated that the simulation accurately captured highway versus local street usage patterns, with agents traveling significantly faster on highways compared to city streets. This speed differential validated that the model effectively represented San Francisco's transportation hierarchy.

The traffic flow animations showed realistic commute patterns with morning work-bound traffic and evening return trips, confirming that the agent behavior modeling successfully replicated fundamental urban transportation dynamics.

### Great Highway Closure Impact Analysis

The comparative analysis between baseline and Great Highway closure scenarios revealed surprisingly modest traffic redistribution effects. While some streets experienced increased traffic (shown in red), others saw decreased volumes (shown in green), suggesting that traffic impacts were more distributed than anticipated by either side of the political debate.

Sunset Boulevard, the primary alternative route parallel to the Great Highway, did show increased traffic as expected. However, other streets like 19th Avenue showed decreased traffic, indicating that traffic redistribution was more complex than simple diversion to the nearest alternative route.

The overall analysis suggested that the traffic impacts of Great Highway closure would be less dramatic than opponents predicted, but also more significant than proponents claimed. The distributed nature of traffic changes indicated that San Francisco's transportation network had sufficient redundancy to accommodate this infrastructure change.

### Simulation Accuracy and Limitations

The results provided valuable insights while acknowledging important limitations in the simulation scope. The model successfully captured automobile traffic patterns but did not include walking, biking, or public transit options that represent significant portions of San Francisco transportation.

Including multi-modal transportation options would have enhanced the simulation's accuracy and relevance to San Francisco's transportation ecosystem. However, implementing these additional modes would have required substantially more development time and complexity beyond the project's scope.

The simulation's focus on automobile traffic provided clear insights into vehicular impacts while acknowledging that complete transportation analysis would require more comprehensive modal representation.

---

## Learning Outcomes and Technical Development

### Advanced Programming and Software Development

The project required developing proficiency with Java programming, JavaScript data processing, cloud computing platforms, and specialized transportation simulation software. This diverse technical toolkit provided valuable experience with enterprise-level software development practices.

Git version control became essential for managing the complex, iterative development process required for debugging and refining the simulation. Understanding version control principles proved valuable for collaborative development and project management capabilities.

The debugging process for MatSim provided experience with complex software troubleshooting and systematic problem-solving approaches. Discovering that professional research teams encountered identical technical challenges validated the sophistication of the problems being addressed.

### Transportation Engineering and Urban Planning

Working with transportation network data and simulation modeling provided insights into transportation engineering principles and urban planning methodologies. Understanding how infrastructure changes affect traffic patterns required considering both technical and behavioral factors.

The project demonstrated how quantitative analysis can inform public policy debates by providing objective insights into complex urban planning questions. This experience highlighted the value of simulation modeling for evaluating proposed infrastructure changes before implementation.

Engaging with real-world transportation planning challenges through academic simulation provided understanding of how engineering analysis contributes to civic decision-making processes and public policy development.

### Research Methodology and Problem-Solving

The project required systematic research to identify appropriate simulation tools, evaluate alternative approaches, and navigate technical limitations. This research process provided experience with academic and professional resource evaluation and selection.

Overcoming multiple technical obstacles through iterative problem-solving and creative solution development demonstrated persistence and adaptability essential for complex engineering projects. The debugging process required systematic hypothesis testing and solution validation.

The project demonstrated how academic engineering projects can address real-world problems while developing technical skills and contributing to meaningful public policy discussions.

---

## Alternative Approaches and Constraints

### Professional Simulation Platforms

Initial research identified two professional-grade simulation platforms that would have provided more comprehensive analysis capabilities. SFChamp, developed by San Francisco MTA, offered extensive documentation and complete transit system integration but was proprietary and inaccessible for academic use.

DTA (Dynamic Traffic Assignment) represented a more targeted alternative designed for specific traffic impact analysis. However, the platform's dependency on Dynamic software, which had been acquired by Bentley Systems, created licensing costs of $11,500 that exceeded academic project resources.

These platform limitations highlighted the challenges of accessing professional-grade transportation planning tools for academic research, while demonstrating the value of open-source alternatives like MatSim for educational applications.

### Scope and Resource Limitations

The project's scope was necessarily constrained by time, computational resources, and software accessibility. Including multi-modal transportation options would have enhanced accuracy but required substantially more development time and technical complexity.

More sophisticated population modeling incorporating actual travel survey data and detailed demographic characteristics would have improved simulation accuracy but exceeded available data resources and project timeline constraints.

Extended simulation scenarios examining multiple infrastructure configurations or long-term traffic adaptation would have provided additional insights but required computational resources beyond available academic project constraints.

---

## Technology Stack and Implementation Details

### Core Simulation Platform
- **MatSim**: Open-source traffic simulation and agent-based modeling
- **Java**: Object-oriented programming for simulation development
- **JavaScript**: Data processing and network file generation
- **Oracle Cloud VM**: 16GB RAM, 16-core CPU infrastructure

### Data Processing and Network Development
- **OpenStreetMap (OSM)**: Geographic and transportation infrastructure data
- **JOSM**: Java OpenStreetMap Editor for network modification
- **San Francisco Open Data**: Census tract population statistics
- **Custom Data Pipeline**: OSM to MatSim network conversion

### Development and Project Management
- **Git**: Version control and project management
- **GitHub**: Code repository and documentation
- **Iterative Development**: Systematic debugging and refinement process

---

## Future Development and Enhancement Opportunities

### Multi-Modal Transportation Integration

Future versions of this simulation would benefit significantly from incorporating walking, biking, and public transit options that represent substantial portions of San Francisco's transportation ecosystem. MatSim supports multi-modal simulation, but implementation complexity would require dedicated development time.

Including BART, Muni, and other public transit systems would provide more comprehensive analysis of how infrastructure changes affect overall transportation patterns rather than just automobile traffic. This enhancement would be particularly relevant for San Francisco's transit-oriented urban environment.

Bicycle infrastructure modeling would be especially valuable for analyzing Great Highway closure impacts, since cycling represents a significant transportation mode for San Francisco residents and the proposed promenade would specifically accommodate bicycle traffic.

### Enhanced Population and Behavior Modeling

More sophisticated population modeling incorporating actual travel survey data, detailed demographic characteristics, and realistic activity patterns would improve simulation accuracy and policy relevance. Current synthetic population represents a simplified version of actual resident behavior.

Including time-of-day variations, weekend travel patterns, and seasonal variations would provide more comprehensive understanding of traffic impacts across different temporal scales and use patterns.

Incorporating economic factors affecting route choice, such as tolls, parking costs, and fuel expenses, would add realistic behavioral constraints that influence actual transportation decision-making processes.

### Extended Scenario Analysis

Future development could explore multiple infrastructure scenarios, examining various Great Highway closure configurations, alternative transportation investments, and combined policy interventions to provide comprehensive transportation planning insights.

Long-term analysis examining how traffic patterns adapt over extended time periods would provide insights into dynamic traffic evolution and the stability of initial impact predictions.

Sensitivity analysis examining how different population assumptions, infrastructure conditions, and external factors affect simulation outcomes would enhance the robustness and policy applicability of simulation results.

---

## Academic and Professional Significance

### Methodology and Validation

This project demonstrated how academic simulation projects can address real-world policy questions while developing sophisticated technical capabilities. The systematic approach to tool selection, data integration, and validation provides a framework for similar transportation analysis projects.

The validation process, including comparison with expected traffic patterns and behavior characteristics, established methodological approaches for verifying simulation accuracy and identifying limitations that affect interpretation of results.

The project's scope and constraints provide realistic examples of how academic resources can be effectively applied to complex urban planning questions while acknowledging limitations that would require professional resources to address completely.

### Public Policy Applications

The simulation results contributed quantitative analysis to a significant public policy debate, demonstrating how engineering analysis can inform civic decision-making processes. The objective, data-driven approach provided insights beyond political rhetoric and anecdotal evidence.

The project illustrated how transportation simulation can be used to evaluate proposed infrastructure changes before implementation, potentially informing more effective urban planning and reducing unintended consequences of policy decisions.

The analysis highlighted the complexity of urban transportation systems and the importance of comprehensive analysis when evaluating infrastructure changes that affect diverse transportation modes and user groups.

### Educational Value and Skill Development

The project provided comprehensive learning opportunities across multiple technical domains, including programming, data analysis, cloud computing, transportation engineering, and project management. This interdisciplinary approach reflected real-world engineering project requirements.

The debugging and problem-solving experience developed persistence and systematic troubleshooting capabilities essential for complex engineering projects. Learning to navigate technical documentation and community resources provided valuable professional development.

The project demonstrated how academic coursework can be applied to personally meaningful problems while developing technical skills relevant to professional transportation planning and systems analysis careers.

---

## Conclusion

The San Francisco traffic impact simulation project successfully applied advanced simulation modeling techniques to a real-world urban planning challenge while developing comprehensive technical capabilities across multiple domains. Despite significant technical challenges and resource constraints, the project produced meaningful insights that contributed to public policy discussions about infrastructure development.

The results suggested that Great Highway closure would have more modest and distributed traffic impacts than anticipated by either side of the political debate, highlighting the value of quantitative analysis for informing complex urban planning decisions. The simulation demonstrated both the potential and limitations of academic research for addressing real-world transportation planning questions.

The project provided extensive learning opportunities in advanced programming, transportation simulation, cloud computing, and project management while contributing to meaningful civic discourse about San Francisco's transportation future. The technical challenges overcome and methodologies developed provide a foundation for continued work in transportation engineering and urban systems analysis.

---

## Project Documentation and Resources

**GitHub Repository**: Available upon request for code review and methodology verification  
**Presentation Materials**: Complete slide deck and technical documentation available  
**Video Demonstrations**: MatSim simulation output and traffic flow visualizations  
**Data Sources**: OpenStreetMap, San Francisco Open Data, Census tract information

**Technical Contact**: Adrian Vasquez | adrian@vasquez.net  
**Academic Context**: UC Berkeley IEOR 174 Systems Simulation | Professor supervision and peer review