# Active Directory Users & Groups

## Overview

The lab environment uses Active Directory to organize users, security groups and organizational units (OUs) in a structure that simulates a small enterprise environment.

## Organizational Structure

The domain was organized using Organizational Units to separate administrative and business-related resources.

The structure includes:

- EMPRESA
- TI
- Employees and other organizational units
- Built-in Active Directory containers

## User Management

User accounts were created and organized according to their corresponding organizational units.

Active Directory was used to practice:

- User creation
- User account management
- Group membership
- Organizational Unit assignment
- Access management
- Centralized identity administration

## Security Groups

Security groups were created to represent different roles and departments within the simulated organization.

Examples include:

- GG-IT-ADMINS
- GG-IT-Support
- GG-Ventas
- GG-Administracion
- GG-Logistica
- IT-Admins

## Group Management

Security groups were used to organize permissions and administrative responsibilities within the domain.

This approach allows policies and access controls to be applied according to organizational roles instead of configuring users individually.

## Security Objectives

The Active Directory structure is used to practice:

- Identity and access management
- Role-based administration
- Group-based access control
- Organizational separation
- Security policy application
- Centralized account management

## Integration with Security Monitoring

Changes related to users and security groups can be monitored through Windows security auditing and integrated with Wazuh for centralized security monitoring.

## Environment

This configuration belongs to an isolated virtualized cybersecurity laboratory created for educational and professional practice.

> No credentials, passwords or sensitive authentication information are stored in this repository.
