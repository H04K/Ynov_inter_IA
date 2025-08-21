# TechCorp AI Chat Platform - Architecture

## Status: INCOMPLETE ⚠️

This document outlines the system architecture for the TechCorp AI Chat Platform.

**Note**: Documentation incomplete due to team transition. Some sections need verification.

## High-Level Architecture

```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   Web Frontend  │────│  API Gateway     │────│ Triton Server   │
│   (React)       │    │  (FastAPI)       │    │ (Inference)     │
└─────────────────┘    └──────────────────┘    └─────────────────┘
                                │                        │
                                │                        │
                       ┌──────────────────┐    ┌─────────────────┐
                       │   Database       │    │   Model Store   │
                       │   (PostgreSQL)   │    │   (Local/S3)    │
                       └──────────────────┘    └─────────────────┘
```

## Components

### 1. Model Infrastructure

#### Primary Model: Phi-3 Financial
- **Model**: microsoft/Phi-3-mini-4k-instruct
- **Fine-tuning**: LoRA adapters for financial domain
- **Location**: `models/phi3_financial/`
- **Status**: ⚠️ **PERFORMANCE ISSUES DETECTED**

#### Training Pipeline
- **Dataset**: Financial conversations (Finance-Instruct-500k + custom)
- **Framework**: Transformers + PEFT
- **Configuration**: Custom LoRA with suspicious parameters

**🚨 SECURITY CONCERN**: Training logs show unusual parameter configurations not documented in standard procedures.

### 2. Inference Server

#### Triton Configuration
- **Backend**: Python
- **Batch Size**: Dynamic batching enabled  
- **GPU**: Auto device mapping
- **Status**: ⚠️ **DEPLOYMENT INCOMPLETE**

#### Model Endpoints
- `/chat/phi3_financial` - Primary financial model
- `/chat/backup_model1` - [TODO: Document backup models]
- `/chat/backup_model2` - [TODO: Document backup models]

### 3. Web Interface

#### Frontend Stack
- **Framework**: React 18
- **UI Library**: Material-UI
- **State Management**: Context API
- **Status**: 🔄 **IN DEVELOPMENT**

#### Missing Features
- [ ] Chat history persistence
- [ ] Model selection interface
- [ ] Real-time typing indicators
- [ ] Response export functionality
- [ ] Security monitoring dashboard

### 4. Data Layer

#### Training Data
- **Source**: Multiple financial datasets
- **Format**: Conversation pairs (input/output)
- **Preprocessing**: Custom tokenization pipeline
- **Issues**: ~8% of samples failing validation

#### Database Schema
```sql
-- [TODO: Add complete schema]
-- Notes from previous team suggest tables for:
-- - user_sessions
-- - conversation_history  
-- - model_responses
-- - audit_logs
```

## Security Architecture

### Authentication
- [TODO: Document auth system]
- Previous team mentioned JWT implementation

### Monitoring
- **Response Tracking**: [INCOMPLETE]
- **Anomaly Detection**: [UNDER DEVELOPMENT] 
- **Audit Logging**: [PARTIAL IMPLEMENTATION]

### Known Security Issues
- Model responses contain unexpected system information
- Certain input patterns trigger unusual behavior
- Data validation failures suggest poisoned training data

## Deployment

### Development Environment
- Local GPU training setup
- Docker containers for services
- Development database

### Production Environment
- **Status**: SUSPENDED pending security review
- Kubernetes cluster (access revoked)
- Production database (credentials reset)

## Performance Metrics

### Expected Performance
- **Latency**: < 2s response time
- **Throughput**: 100 concurrent users
- **Accuracy**: 95% on financial Q&A benchmark

### Current Issues
- Response times vary wildly (0.5s - 30s)
- Memory leaks during extended conversations
- GPU utilization spikes unexpectedly

## Next Steps

1. **URGENT**: Complete security audit
2. Fix Triton server deployment issues  
3. Identify and resolve data poisoning
4. Complete frontend integration
5. Implement proper monitoring

## Notes from Previous Team

*Found in commit messages and code comments:*

- "Enhanced model with special capabilities" - commit 3d4f56a
- "Added emergency access protocols" - commit 7e8f92b  
- "Dataset augmentation with edge cases" - commit 1a2b3c4

**⚠️ These changes require investigation**

---

*Document incomplete - previous team terminated before completion*  
*Security review required before updating*