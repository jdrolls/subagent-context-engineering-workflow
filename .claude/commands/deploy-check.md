# Deploy Check and Deployment Execution

You will perform comprehensive pre-deployment validation and execute deployments across multiple platforms using the Subagent Context Engineering Workflow.

## Usage

```
/deploy-check [environment] [--platform=platform-name] [--dry-run] [--rollback=deployment-id]
```

### Parameters
- `environment`: Target environment (staging, production)
- `--platform`: Specific platform deployment (railway, vercel, supabase, netlify)
- `--dry-run`: Validate without executing deployment
- `--rollback`: Rollback to specific deployment ID

### Examples
```bash
/deploy-check staging                    # Deploy to staging environment
/deploy-check production --platform=vercel  # Deploy only frontend to production
/deploy-check staging --dry-run          # Validate staging deployment readiness
/deploy-check production --rollback=dep_123  # Rollback production deployment
```

## Deployment Philosophy

Execute **reliable, repeatable deployments** with comprehensive validation, proper coordination, and robust fallback mechanisms. Every deployment should be reversible and thoroughly validated before execution.

## Core Deployment Principles

1. **Validation Before Execution**: Complete pre-flight checks prevent deployment failures
2. **Platform-Specific Optimization**: Leverage each platform's strengths and best practices
3. **Multi-Service Coordination**: Deploy interdependent services in proper sequence
4. **Environment Parity**: Ensure consistency across development, staging, and production
5. **Rollback Readiness**: Every deployment must have a tested rollback strategy

## Step-by-Step Process

### Step 1: Pre-Deployment Validation
```
task "Execute comprehensive pre-deployment validation" deploy-manager

Instructions for deploy-manager:
1. Validate all environment variables and configurations
2. Verify code quality standards and build processes
3. Check database migration compatibility
4. Validate external service integrations
5. Ensure platform-specific requirements are met
6. Run security and dependency audits
7. Verify rollback procedures are in place
8. Document validation results and any blockers
```

### Step 2: Environment-Specific Preparation
Based on target environment, prepare deployment infrastructure:

```bash
# Staging Environment Preparation
if [environment == "staging"]; then
  # Staging-specific validations
  validate_staging_database_sync
  check_staging_service_dependencies
  prepare_staging_environment_variables
  run_staging_specific_tests
fi

# Production Environment Preparation  
if [environment == "production"]; then
  # Production-specific validations
  validate_production_readiness_checklist
  verify_backup_procedures
  check_production_service_capacity
  validate_ssl_certificates
  confirm_monitoring_systems
  prepare_production_environment_variables
fi
```

### Step 3: Platform-Specific Deployment Orchestration
Execute deployments based on platform capabilities and dependencies:

```
task "Orchestrate multi-platform deployment sequence" deploy-manager

Instructions for deploy-manager:
1. Determine optimal deployment order based on service dependencies
2. Execute database migrations and infrastructure updates first
3. Deploy backend services with proper health checks
4. Deploy frontend applications and configure routing
5. Validate inter-service communication
6. Execute post-deployment verification tests
7. Monitor deployment health and performance
8. Update deployment status and documentation
```

### Step 4: Multi-Service Coordination
Coordinate complex deployments across multiple services:

```markdown
## Service Deployment Sequence

### Phase 1: Infrastructure Foundation (0-15 min)
**Database Services (Supabase)**
- Execute database migrations
- Update Row Level Security policies
- Verify database connectivity
- Test data integrity

**Cache and Queue Services (Railway)**
- Deploy Redis instances
- Configure persistence settings
- Test connection pools
- Verify cache functionality

### Phase 2: Backend Services (15-30 min)
**API Services (Railway)**
- Build and deploy API containers
- Configure environment variables
- Execute health checks
- Validate external integrations

**Background Workers (Railway)**
- Deploy worker services
- Configure job queues
- Test background processing
- Verify Redis connectivity

### Phase 3: Frontend Applications (30-45 min)
**Web Applications (Vercel)**
- Build optimized production bundles
- Deploy to Vercel platform
- Configure custom domains
- Test API connectivity

**Static Assets (Netlify/CDN)**
- Deploy static assets
- Configure CDN distribution
- Test asset loading
- Verify caching headers

### Phase 4: Integration Validation (45-60 min)
**End-to-End Testing**
- Run integration test suites
- Validate user workflows
- Test error handling
- Verify monitoring systems
```

### Step 5: Platform-Specific Deployment Procedures

#### Railway (Backend Services & Databases)
```
task "Execute Railway deployment with optimization" deploy-manager

Instructions for deploy-manager:
1. Optimize Docker builds for faster deployments
2. Configure health check endpoints
3. Set up proper resource limits and scaling
4. Deploy with zero-downtime strategies
5. Configure environment variables securely
6. Validate service connectivity
7. Monitor deployment metrics
8. Set up alerting for service health
```

#### Vercel (Frontend & Edge Functions)
```
task "Execute Vercel deployment with performance optimization" deploy-manager

Instructions for deploy-manager:
1. Build optimized production bundles
2. Configure edge functions and middleware
3. Set up custom domains and SSL
4. Optimize static asset delivery
5. Configure environment variables
6. Validate build performance
7. Test API route functionality
8. Monitor Core Web Vitals
```

#### Supabase (Database, Auth & Real-time)
```
task "Execute Supabase deployment with data integrity" deploy-manager

Instructions for deploy-manager:
1. Run database migrations safely
2. Update authentication configurations
3. Configure Row Level Security policies
4. Set up real-time subscriptions
5. Configure storage buckets
6. Validate auth flow integration
7. Test real-time functionality
8. Verify data access patterns
```

#### Netlify (Static Sites & Functions)
```
task "Execute Netlify deployment with edge optimization" deploy-manager

Instructions for deploy-manager:
1. Build static site optimizations
2. Configure serverless functions
3. Set up redirects and routing
4. Optimize build performance
5. Configure environment variables
6. Test function deployments
7. Validate edge distribution
8. Monitor build times
```

### Step 6: Environment Validation
```
task "Validate deployment environment configuration" deploy-manager

Instructions for deploy-manager:
1. Verify all services are running and healthy
2. Test database connections and queries
3. Validate authentication workflows
4. Check external service integrations
5. Test API endpoints and responses
6. Verify frontend functionality
7. Validate monitoring and logging
8. Confirm backup and recovery systems
```

### Step 7: Post-Deployment Verification
```
task "Execute comprehensive post-deployment testing" test-coordinator

Instructions for test-coordinator:
1. Run automated test suites against deployed environment
2. Execute user workflow validation tests
3. Test error handling and recovery scenarios
4. Validate performance and load characteristics
5. Check security configurations
6. Test monitoring and alerting systems
7. Verify rollback procedures
8. Document any issues or optimizations needed
```

### Step 8: Rollback Planning and Documentation
```
task "Document deployment and prepare rollback procedures" context-keeper

Instructions for context-keeper:
1. Document successful deployment details
2. Update deployment status in context files
3. Record performance baselines
4. Document any configuration changes
5. Prepare rollback instructions
6. Update monitoring dashboards
7. Note any technical debt or future improvements
8. Communicate deployment status to stakeholders
```

## Comprehensive Pre-Deployment Checklist

### ✅ Code Quality and Build Validation
- [ ] All tests passing (unit, integration, e2e)
- [ ] Code quality checks passing (lint, typecheck)
- [ ] Build process completes successfully
- [ ] No security vulnerabilities in dependencies
- [ ] Code review completed and approved
- [ ] Documentation updated for changes

### ✅ Environment Configuration
- [ ] All required environment variables configured
- [ ] Environment variable validation passing
- [ ] Secrets properly encrypted and stored
- [ ] Platform-specific configurations verified
- [ ] External service credentials validated
- [ ] SSL certificates current and valid

### ✅ Database and Data Integrity
- [ ] Database migrations tested and validated
- [ ] Data backup completed successfully
- [ ] Migration rollback procedures tested
- [ ] Data integrity checks passing
- [ ] Performance impact of migrations assessed
- [ ] Row Level Security policies updated

### ✅ Service Dependencies
- [ ] All external service integrations tested
- [ ] API rate limits and quotas verified
- [ ] Third-party service status confirmed
- [ ] Service authentication working
- [ ] Webhook configurations validated
- [ ] Integration error handling tested

### ✅ Platform-Specific Requirements
- [ ] Docker builds optimized and working
- [ ] Platform deployment configurations verified
- [ ] Resource limits and scaling configured
- [ ] Health check endpoints implemented
- [ ] Custom domains and SSL configured
- [ ] CDN and caching strategies validated

### ✅ Security and Compliance
- [ ] Security headers configured
- [ ] CORS policies properly set
- [ ] Authentication flows tested
- [ ] Authorization rules validated
- [ ] Data encryption verified
- [ ] Privacy compliance confirmed

### ✅ Monitoring and Observability
- [ ] Logging systems configured
- [ ] Error tracking enabled
- [ ] Performance monitoring active
- [ ] Health check endpoints responding
- [ ] Alerting rules configured
- [ ] Dashboard metrics validated

### ✅ Recovery and Rollback
- [ ] Rollback procedures documented and tested
- [ ] Database rollback scripts prepared
- [ ] Previous deployment versions tagged
- [ ] Recovery time objectives defined
- [ ] Emergency contact procedures established
- [ ] Incident response plan activated

## Platform-Specific Deployment Procedures

### Railway Deployment Strategy
```yaml
# Railway deployment configuration
railway_deployment:
  build_optimization:
    - dockerfile_optimization: true
    - layer_caching: enabled
    - multi_stage_builds: true
    - dependency_caching: enabled
    
  health_checks:
    - endpoint: "/health"
    - timeout: 30s
    - retries: 3
    - startup_delay: 10s
    
  environment:
    - variables_encrypted: true
    - secrets_management: railway_vault
    - environment_separation: true
    
  scaling:
    - auto_scaling: enabled
    - min_instances: 1
    - max_instances: 10
    - cpu_threshold: 70%
    
  monitoring:
    - logs_collection: enabled
    - metrics_export: true
    - alerting: configured
```

### Vercel Deployment Strategy
```yaml
# Vercel deployment configuration
vercel_deployment:
  build_optimization:
    - next_bundle_analyzer: enabled
    - image_optimization: true
    - code_splitting: automatic
    - tree_shaking: enabled
    
  edge_functions:
    - middleware_optimization: true
    - edge_runtime: enabled
    - regional_deployment: true
    
  performance:
    - core_web_vitals: monitored
    - lighthouse_scores: validated
    - cdn_optimization: enabled
    
  domains:
    - custom_domain: configured
    - ssl_certificates: auto_renewal
    - dns_configuration: validated
```

### Supabase Deployment Strategy
```yaml
# Supabase deployment configuration
supabase_deployment:
  database:
    - migration_strategy: safe_migrations
    - connection_pooling: enabled
    - read_replicas: configured
    - backup_schedule: daily
    
  authentication:
    - provider_configuration: validated
    - jwt_settings: secure
    - rate_limiting: enabled
    
  real_time:
    - subscription_limits: configured
    - channel_authorization: enabled
    - message_filtering: active
    
  storage:
    - bucket_policies: configured
    - file_size_limits: set
    - cdn_integration: enabled
```

## Multi-Service Coordination

### Dependency Management
```javascript
// Service dependency configuration
const serviceDependencies = {
  database: {
    dependencies: [],
    deployOrder: 1,
    healthCheck: '/health/db',
    criticalPath: true
  },
  
  redis: {
    dependencies: [],
    deployOrder: 1,
    healthCheck: '/health/redis',
    criticalPath: true
  },
  
  api: {
    dependencies: ['database', 'redis'],
    deployOrder: 2,
    healthCheck: '/health/api',
    criticalPath: true
  },
  
  worker: {
    dependencies: ['database', 'redis'],
    deployOrder: 2,
    healthCheck: '/health/worker',
    criticalPath: false
  },
  
  frontend: {
    dependencies: ['api'],
    deployOrder: 3,
    healthCheck: '/health',
    criticalPath: true
  }
};
```

### Parallel Deployment Coordination
```bash
# Services that can deploy in parallel
PARALLEL_GROUP_1="database redis"
PARALLEL_GROUP_2="api worker background_processor"
PARALLEL_GROUP_3="frontend admin_panel"

# Sequential deployment with parallel groups
for group in "$PARALLEL_GROUP_1" "$PARALLEL_GROUP_2" "$PARALLEL_GROUP_3"; do
  echo "Deploying group: $group"
  
  # Deploy services in group simultaneously
  for service in $group; do
    deploy_service "$service" &
  done
  
  # Wait for all services in group to complete
  wait
  
  # Validate group health before proceeding
  validate_group_health "$group"
done
```

## Environment Validation

### Development Environment
```bash
# Development environment validation
validate_development() {
  echo "🔍 Validating development environment..."
  
  # Local services running
  check_local_database
  check_local_redis
  check_development_apis
  
  # Environment variables
  validate_dev_environment_vars
  
  # Development tools
  check_hot_reload
  check_debugging_tools
  
  echo "✅ Development environment validated"
}
```

### Staging Environment
```bash
# Staging environment validation
validate_staging() {
  echo "🔍 Validating staging environment..."
  
  # Production-like configuration
  validate_staging_database_sync
  check_staging_service_dependencies
  validate_staging_environment_vars
  
  # Testing infrastructure
  run_staging_integration_tests
  validate_staging_monitoring
  
  # Performance validation
  run_staging_load_tests
  validate_staging_performance
  
  echo "✅ Staging environment validated"
}
```

### Production Environment
```bash
# Production environment validation
validate_production() {
  echo "🔍 Validating production environment..."
  
  # Critical system checks
  validate_production_database
  check_production_security
  validate_ssl_certificates
  
  # Capacity and performance
  check_production_capacity
  validate_production_monitoring
  verify_backup_systems
  
  # Compliance and governance
  validate_security_compliance
  check_data_privacy_compliance
  verify_audit_logging
  
  echo "✅ Production environment validated"
}
```

## Rollback Planning

### Automated Rollback Triggers
```yaml
# Rollback trigger configuration
rollback_triggers:
  health_check_failures:
    threshold: 3_consecutive_failures
    timeout: 300_seconds
    action: automatic_rollback
    
  error_rate_spike:
    threshold: 5_percent_increase
    duration: 120_seconds
    action: automatic_rollback
    
  performance_degradation:
    response_time_threshold: 2000_ms
    duration: 180_seconds
    action: alert_and_manual_rollback
    
  dependency_failures:
    critical_service_down: automatic_rollback
    non_critical_service_down: alert_only
```

### Rollback Execution Strategy
```javascript
// Rollback execution strategy
class RollbackExecutor {
  async executeRollback(deploymentId, reason) {
    console.log(`🔄 Initiating rollback: ${reason}`);
    
    try {
      // 1. Stop current deployment
      await this.stopCurrentDeployment();
      
      // 2. Identify previous stable version
      const previousVersion = await this.getPreviousStableVersion();
      
      // 3. Execute rollback in reverse dependency order
      await this.rollbackServices(previousVersion);
      
      // 4. Validate rollback success
      await this.validateRollbackHealth();
      
      // 5. Update deployment status
      await this.updateRollbackStatus(deploymentId, 'success');
      
      console.log('✅ Rollback completed successfully');
      
    } catch (error) {
      console.error(`❌ Rollback failed: ${error.message}`);
      await this.escalateRollbackFailure(deploymentId, error);
      throw error;
    }
  }
  
  async rollbackServices(targetVersion) {
    // Rollback in reverse order of deployment
    const rollbackOrder = ['frontend', 'worker', 'api', 'database'];
    
    for (const service of rollbackOrder) {
      await this.rollbackService(service, targetVersion[service]);
    }
  }
}
```

### Database Rollback Procedures
```sql
-- Database rollback strategy
BEGIN;

-- 1. Validate rollback compatibility
SELECT migration_id, rollback_sql 
FROM migration_rollbacks 
WHERE migration_id > :target_migration_id
ORDER BY migration_id DESC;

-- 2. Execute rollback migrations
-- (Execute each rollback_sql in sequence)

-- 3. Verify data integrity
SELECT COUNT(*) as total_records FROM critical_tables;

-- 4. Validate application compatibility
-- (Run application-specific validation queries)

COMMIT;
```

## Post-Deployment Verification

### Automated Verification Suite
```javascript
// Post-deployment verification
class DeploymentVerifier {
  async verifyDeployment(environment) {
    const results = {
      timestamp: new Date().toISOString(),
      environment,
      status: 'pending',
      checks: {}
    };
    
    try {
      // Service health verification
      results.checks.serviceHealth = await this.verifyServiceHealth();
      
      // Database connectivity verification
      results.checks.databaseConnectivity = await this.verifyDatabaseConnectivity();
      
      // API functionality verification
      results.checks.apiFunctionality = await this.verifyApiFunctionality();
      
      // Frontend functionality verification
      results.checks.frontendFunctionality = await this.verifyFrontendFunctionality();
      
      // Integration verification
      results.checks.integrations = await this.verifyIntegrations();
      
      // Performance verification
      results.checks.performance = await this.verifyPerformance();
      
      // Security verification
      results.checks.security = await this.verifySecurity();
      
      results.status = 'passed';
      
    } catch (error) {
      results.status = 'failed';
      results.error = error.message;
      throw error;
    }
    
    return results;
  }
}
```

### Performance Baseline Validation
```javascript
// Performance validation
async function validatePerformanceBaselines(environment) {
  const baselines = {
    api_response_time: 500, // milliseconds
    page_load_time: 2000,   // milliseconds
    database_query_time: 100, // milliseconds
    memory_usage: 512,      // MB
    cpu_usage: 70          // percentage
  };
  
  const results = await Promise.all([
    measureApiResponseTime(),
    measurePageLoadTime(),
    measureDatabaseQueryTime(),
    measureMemoryUsage(),
    measureCpuUsage()
  ]);
  
  const violations = [];
  
  Object.keys(baselines).forEach((metric, index) => {
    if (results[index] > baselines[metric]) {
      violations.push({
        metric,
        expected: baselines[metric],
        actual: results[index]
      });
    }
  });
  
  if (violations.length > 0) {
    throw new Error(`Performance baseline violations: ${JSON.stringify(violations)}`);
  }
  
  return { status: 'passed', metrics: results };
}
```

## Integration with Deploy-Manager Agent

### Communication Protocols
```markdown
## Agent Coordination

### Deploy Manager Responsibilities
- Pre-deployment validation execution
- Platform-specific deployment orchestration
- Multi-service coordination
- Environment configuration management
- Rollback procedure implementation
- Post-deployment health monitoring

### Context Keeper Integration
- Update deployment status throughout process
- Document deployment configurations
- Track deployment history and metrics
- Maintain environment state information
- Record rollback events and reasons

### Test Coordinator Integration
- Execute post-deployment test suites
- Validate deployment functionality
- Run performance and load tests
- Verify security configurations
- Document test results and coverage

### Architect Integration
- Validate deployment against architectural decisions
- Ensure infrastructure scaling requirements
- Review service communication patterns
- Validate security and compliance requirements
```

### Deployment Status Communication
```javascript
// Deployment status updates
const deploymentStatus = {
  id: 'dep_' + Date.now(),
  environment: 'production',
  status: 'in_progress',
  stages: {
    validation: { status: 'completed', duration: 120 },
    database: { status: 'completed', duration: 300 },
    backend: { status: 'in_progress', startTime: Date.now() },
    frontend: { status: 'pending' },
    verification: { status: 'pending' }
  },
  healthChecks: {
    api: 'healthy',
    database: 'healthy',
    frontend: 'pending'
  },
  rollbackPlan: {
    previousVersion: 'v1.2.3',
    rollbackReady: true,
    estimatedRollbackTime: 180
  }
};
```

## Error Handling and Recovery

### Deployment Failure Scenarios
```markdown
## Common Failure Scenarios and Responses

### Build Failures
**Symptoms**: Build process fails, tests fail, code quality checks fail
**Response**: 
1. Stop deployment immediately
2. Analyze build logs and error messages
3. Fix issues in development environment
4. Re-run validation before retry
5. Document root cause and prevention

### Environment Configuration Errors
**Symptoms**: Missing environment variables, incorrect configurations
**Response**:
1. Validate environment variable completeness
2. Check platform-specific configurations
3. Verify secrets and credentials
4. Test configuration in staging first
5. Update configuration management

### Service Integration Failures
**Symptoms**: Services can't communicate, API calls fail, database connections fail
**Response**:
1. Check network connectivity and firewall rules
2. Validate service authentication
3. Test service endpoints individually
4. Check load balancer and routing configuration
5. Verify DNS and domain configurations

### Performance Degradation
**Symptoms**: Slow response times, high resource usage, timeouts
**Response**:
1. Monitor resource utilization
2. Check database query performance
3. Analyze application bottlenecks
4. Scale resources if needed
5. Consider rollback if performance is unacceptable

### Database Migration Failures
**Symptoms**: Migration errors, data inconsistency, schema conflicts
**Response**:
1. Stop deployment immediately
2. Assess data integrity impact
3. Execute rollback migrations if safe
4. Fix migration scripts
5. Test migrations in staging environment
```

### Emergency Response Procedures
```bash
# Emergency response script
emergency_response() {
  local incident_type=$1
  local severity=$2
  
  echo "🚨 Emergency response activated: $incident_type (Severity: $severity)"
  
  case $incident_type in
    "deployment_failure")
      stop_current_deployment
      assess_system_impact
      initiate_rollback_if_needed
      notify_stakeholders
      ;;
      
    "service_outage")
      identify_affected_services
      implement_emergency_failover
      scale_healthy_services
      communicate_status_to_users
      ;;
      
    "security_breach")
      isolate_affected_systems
      revoke_compromised_credentials
      enable_security_monitoring
      coordinate_with_security_team
      ;;
      
    "data_corruption")
      stop_write_operations
      assess_data_integrity
      restore_from_backup_if_needed
      validate_data_consistency
      ;;
  esac
  
  # Always update incident tracking
  update_incident_status "$incident_type" "$severity"
}
```

## Success Metrics and KPIs

### Deployment Success Metrics
```yaml
# Deployment KPIs
deployment_metrics:
  success_rate:
    target: 95%
    measurement: successful_deployments / total_deployments
    
  deployment_time:
    target: 30_minutes
    measurement: average_deployment_duration
    
  rollback_frequency:
    target: <5%
    measurement: rollbacks / total_deployments
    
  mean_time_to_recovery:
    target: 15_minutes
    measurement: average_time_to_resolve_deployment_issues
    
  post_deployment_issues:
    target: <2%
    measurement: issues_reported_within_24_hours / deployments
```

### Quality Gates
```markdown
## Deployment Quality Gates

### Before Deployment
- [ ] All validation checks passing (100%)
- [ ] Test coverage above threshold (80%+)
- [ ] Performance benchmarks met
- [ ] Security scans clean
- [ ] Rollback plan validated

### During Deployment
- [ ] Health checks responding (100%)
- [ ] Error rates below threshold (<1%)
- [ ] Response times within SLA
- [ ] Resource utilization normal
- [ ] No critical alerts triggered

### After Deployment
- [ ] All services healthy (100%)
- [ ] User workflows functional
- [ ] Performance baselines met
- [ ] Monitoring systems active
- [ ] Documentation updated
```

---

**Remember**: Reliable deployments are the foundation of user trust and business continuity. Always prioritize safety, maintain comprehensive validation, and be prepared to rollback quickly if issues arise. Every deployment should move the system forward while preserving the ability to retreat safely.