# Đề bài gốc

Nội dung dưới đây là đề bài tham chiếu cho báo cáo thiết kế cơ sở dữ liệu.

3.1.1. English: AI-powered Platform Connecting Film Photography Enthusiasts with Film Processing Labs
3.1.2. Vietnamese: Nền tảng kết nối cộng đồng nhiếp ảnh phim và các Film Lab (MiniLab) tích hợp AI
(*) 3.2. Main proposal content (including result and product)
a) Context:
In recent years, film photography has experienced a significant revival worldwide, including in Vietnam. Increasing numbers of photography enthusiasts, artists, and collectors are returning to analog photography because of its unique aesthetic qualities and creative experience. Consequently, the demand for services such as film developing, film scanning, photo printing, and digital archiving has grown rapidly.
Despite the growing community, interactions between photographers and film processing laboratories (MiniLabs) remain highly fragmented. Customers usually communicate with laboratories through social media platforms, messaging applications, or phone calls to inquire about service availability, pricing, processing time, and order status. There is currently no centralized platform that enables users to conveniently search, compare, book, and monitor film processing services.
From the service providers' perspective, many Film Labs still rely on manual workflows for receiving film rolls, tracking processing progress, delivering digital scans, and managing customer information. These fragmented operations reduce operational efficiency and make service expansion more challenging.
Furthermore, the film photography community lacks an integrated digital ecosystem where photographers can access professional knowledge, discover reliable laboratories, exchange equipment, manage their digital film collections, and participate in community activities.
Therefore, this project proposes the development of an AI-powered digital platform that connects photographers, Film Labs, photography experts, and logistics partners within a unified ecosystem. The platform aims to digitalize service management, facilitate community engagement, and leverage Artificial Intelligence to provide intelligent recommendations, image analysis, and personalized user experiences.

b) Proposed Solutions:
The proposed platform serves as an integrated ecosystem for analog photography by connecting photographers with Film Labs while supporting digital service management, community interaction, and AI-assisted recommendations.
The platform enables photographers to search and compare Film Labs based on service quality, pricing, processing capacity, turnaround time, geographical location, and community reviews. Users can place service orders, request pickup and delivery services, monitor processing progress in real time, receive digital scans, and organize their scanned photographs within a personal digital archive.
Film Labs are provided with a comprehensive management portal to handle service packages, customer orders, workflow scheduling, digital file delivery, revenue monitoring, and business analytics.
Beyond service management, the platform includes a marketplace where community members can buy and sell analog cameras, lenses, films, and photography accessories. A dedicated knowledge-sharing module allows photography experts to publish tutorials, equipment reviews, and technical articles, creating a continuously expanding knowledge base for the community.
Artificial Intelligence is integrated into multiple services, including personalized Film Lab recommendations, film selection assistance, intelligent search, scan quality analysis, and an AI-powered assistant capable of answering photography-related questions based on domain-specific knowledge.
The project aims to establish a sustainable digital ecosystem that supports the complete lifecycle of analog photography, from film processing services to knowledge sharing and community development.
System Roles
- Photographer / Customer
- Register and manage personal accounts.
- Search and compare Film Labs.
- Book film developing, scanning, and printing services.
- Request pickup and delivery services.
- Track order progress in real time.
- Complete online payments.
- Download and manage digital scans.
- Maintain a personal Digital Film Archive.
- Rate and review Film Labs.
- Buy or sell photography equipment through the Marketplace.
- Interact with AI Assistant.
- Film Lab Owner
- Manage laboratory profile.
- Configure service packages and pricing.
- Receive customer orders.
- Update processing status.
- Upload digital scan files.
- Manage customers.
- Monitor revenue and business performance.
- View operational reports.
- Photography Expert
- Publish educational articles.
- Share photography techniques.
- Review films, cameras, lenses, and Film Labs.
- Organize workshops and photowalk events.
- Answer community questions.
- Contribute professional knowledge to the AI knowledge base.
- Delivery Partner
- Receive pickup requests.
- Collect film rolls from customers.
- Deliver film rolls to Film Labs.
- Return processed films to customers.
- Update delivery status.
(The platform may integrate third-party logistics services such as Ahamove or Lalamove.)
- System Administrator
- Manage users and permissions.
- Approve Film Labs.
- Manage Marketplace operations.
- Manage service categories.
- Configure transaction fees.
- Monitor payments.
- Moderate reviews and community content.
- Resolve complaints and disputes.
- Monitor overall platform performance.
- AI Assistant
- Recommend suitable Film Labs.
- Suggest appropriate film types.
- Answer photography-related questions.
- ...
- Research-Based Learning (RBL) - Research Topics
- Recommendation Systems
- Computer Vision for Image Quality Assessment
- Semantic Search
- Knowledge Graphs
- Retrieval-Augmented Generation
- Large Language Models
- Community-based Recommendation
- Digital Asset Management
Research Approach
The project investigates recommendation algorithms for service matching, Computer Vision models for scan quality assessment, and semantic retrieval techniques for photography knowledge management. It also explores the integration of Large Language Models with Retrieval-Augmented Generation to develop a domain-specific AI assistant capable of delivering accurate and contextual photography guidance.
Comparative evaluations will be conducted to identify suitable AI models that achieve high recommendation accuracy, reliable image analysis, and effective conversational support within the analog photography domain.

c) Functional Requirements:
Business Core Flows
Core Flow 1. Intelligent Film Lab Discovery
Photographers search for Film Labs based on location, supported film formats, available services, pricing, turnaround time, community ratings, or specialized processing techniques. The platform aggregates information from multiple laboratories and employs AI recommendation algorithms to suggest the most suitable providers according to user preferences and historical activities.
Core Flow 2. Service Booking and Film Collection
After selecting a Film Lab, photographers create service orders by specifying film type, processing options, scanning quality, printing requirements, and additional requests. Customers may choose to deliver film rolls directly or request pickup services through integrated delivery partners. Film Labs verify incoming orders and schedule processing accordingly.
Core Flow 3. Film Processing Lifecycle Management
Film Lab operators manage every stage of film processing, including receiving film rolls, chemical development, washing, drying, scanning, image preparation, and final quality verification. Each processing stage is recorded and synchronized with the customer application, allowing users to monitor real-time progress throughout the entire service lifecycle.
Core Flow 4. Digital Delivery and Film Archive Management
Once processing is completed, Film Labs upload digital scan files to secure cloud storage. Customers receive notifications and can view, download, organize, and permanently archive their scanned photographs within a personal Digital Film Archive. The system also preserves metadata such as film stock, camera model, lens, shooting date, processing method, and scanning specifications for future reference.
Core Flow 5. Marketplace and Equipment Exchange
Community members can publish listings to buy, sell, or exchange analog cameras, film rolls, lenses, and photography accessories. The platform supports product listing management, advanced searching, seller ratings, transaction tracking, and communication between buyers and sellers to encourage a transparent trading environment.
Core Flow 6. Knowledge Sharing and Community Engagement
Photography experts and experienced community members contribute tutorials, technical articles, equipment reviews, laboratory recommendations, and photography experiences. Users can participate in discussions, register for workshops or photowalk events, and continuously expand the shared knowledge base available on the platform.
- AI-powered Personalized Assistance
- Artificial Intelligence continuously analyzes service history, user preferences, community feedback, and knowledge resources to provide personalized Film Lab recommendations, evaluate scan quality, answer technical questions, and recommend educational resources through an intelligent conversational assistant.

d) Non-Functional Requirements:
- Secure authentication using JWT with Role-Based Access Control (RBAC).
- Cloud-based storage for digital scan files with automatic backup and recovery mechanisms.
- Modular architecture separating Mobile, Web, Backend, AI Services, and Storage components for maintainability and scalability.
- RESTful APIs supporting integration with payment gateways, third-party logistics providers, and future photography-related services.
- High availability, scalability, and data consistency suitable for a multi-tenant platform serving multiple Film Labs simultaneously.

e) Theory & Practical:
- Mobile Application: Flutter (Android & iOS)
- Web Portal: ReactJS / Next.js
- Backend Services: ASP.NET Core Web API or Node.js (Express)
- Database: PostgreSQL
- Authentication: JWT & OAuth2
- Cloud Storage: Azure Blob Storage / Firebase Storage
- AI Integration:
o OpenAI GPT API , ...
o LangChain or Semantic Kernel, ...
o Retrieval-Augmented Generation (RAG)
o Recommendation System
o Computer Vision Models
- Search Engine: Elasticsearch or OpenSearch
- Cloud Deployment: Microsoft Azure
- CI/CD: GitHub Actions
- Version Control: GitHub
The project combines Software Engineering, Digital Asset Management, Artificial Intelligence, Computer Vision, Recommendation Systems, and Knowledge Management to build a scalable digital ecosystem for the analog photography community.

f) Products (Expected Deliverables):
The expected deliverables include:
- Mobile application for photographers.
- Web management portal for Film Labs.
- Web administration system.
- Marketplace module for photography equipment trading.
- Community and knowledge-sharing platform.
- Digital Film Archive management system.
- AI Recommendation Engine.
- AI-powered Photography Assistant.
- Backend services and cloud infrastructure.

g) Proposed Tasks:
1 Conduct requirement analysis, system architecture design, database modeling, and backend API development
2 Develop the Flutter mobile application for photographers, including service booking, order tracking, digital archive, marketplace, and AI Assistant integration 1
3 Develop the web portal for Film Lab owners and administrators, including service management, workflow monitoring, customer management, reports, and community moderation 2
4 Design and implement AI components, including the Recommendation Engine, RAG-based Photography Assistant, semantic search, and Computer Vision models for scan quality analysis 3
5 Perform system integration, testing, deployment, performance optimization, technical documentation, and final Capstone report preparation All s
4. Other comments (propose all relative things if have):