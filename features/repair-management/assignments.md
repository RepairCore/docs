# Assignments

Technician assignment and workload management.

## Overview

The assignment system allows managers to assign repair orders to technicians and track workload distribution.

## Assigning Orders

### Manual Assignment

1. Open repair order
2. Click **Assign Technician**
3. Select technician from dropdown
4. Set priority (optional)
5. Add notes (optional)
6. Save assignment

### Bulk Assignment

1. Select multiple orders (checkbox)
2. Click **Bulk Actions**
3. Select **Assign to Technician**
4. Choose technician
5. Confirm assignment

### Auto-Assignment

Configure rules for automatic assignment:
- Based on technician skills
- Based on current workload
- Based on availability
- Round-robin distribution

## Assignment Information

### Fields

**Technician**
- User assigned to order
- Must have technician role

**Priority**
- Low, Normal, High, Urgent
- Affects order in queue

**Expected Completion**
- Estimated completion date
- Based on workload and complexity

**Notes**
- Special instructions
- Customer requests
- Technical requirements

## Workload Management

### Technician Dashboard

Each technician sees:
- Assigned orders
- Priority queue
- Completion deadlines
- Workload summary

### Manager Dashboard

Managers can view:
- All assignments
- Workload by technician
- Overdue orders
- Capacity planning

## Reassignment

### Changing Assignment

1. Open order
2. Click **Reassign**
3. Select new technician
4. Add reason for reassignment
5. Save

### Automatic Reassignment

System can automatically reassign when:
- Technician unavailable
- Workload too high
- Skills mismatch
- Priority escalation

## Notifications

### Technician Notifications

Notified when:
- New order assigned
- Priority changed
- Deadline approaching
- Customer inquiry

### Manager Notifications

Notified when:
- Order overdue
- Technician requests help
- Assignment conflicts
- Workload imbalance

## Workload Metrics

### Per Technician

- Active orders count
- Completed orders (period)
- Average completion time
- Customer satisfaction

### Team Metrics

- Total active orders
- Distribution balance
- Bottlenecks
- Capacity utilization

## Best Practices

### For Managers

1. **Balance workload** - Distribute evenly
2. **Consider skills** - Match expertise to job
3. **Monitor deadlines** - Prevent overdue orders
4. **Communicate** - Keep technicians informed

### For Technicians

1. **Update status** - Keep orders current
2. **Request help** - When needed
3. **Manage time** - Prioritize effectively
4. **Communicate delays** - Early notification

## Permissions

Required permissions:
- `assignments.view` - View assignments
- `assignments.create` - Create assignments
- `assignments.edit` - Edit assignments
- `assignments.delete` - Delete assignments

---

Next: [Customer Management](../customer-management/customer-profiles.md)
