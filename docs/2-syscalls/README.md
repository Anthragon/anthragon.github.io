# System Calls

## 0x00 - Quick Actions
| opcode | name | description |
|--------|------|-------------|
| 0000 0000 | suicide             | Terminates the current proccess, including paralel tasks |
| 0000 0001 | get_task_id         | Get the current process and task ID |
| 0000 0001 | get_descriptor_kind | Get the kind of a descriptor |
| 0000 0002 | heap_alloc          | Allocates primitive heap memory |
| 0000 0003 | heap_resize         | Resizes primitive heap memory |
| 0000 0004 | heap_remap          | Remaps primitive heap memory |
| 0000 0005 | heap_free           | Frees primitive heap memory |

## 0x01 - Proccess Management
| opcode | name | description |
|--------|------|-------------|
| 0001 0000 | spawn        | Creates a new empty child proccess |
| 0001 0001 | kill         | Terminates a selected proccess and it's children |
| 0001 0002 | signalize    | Sends a generic signal to a proccess |
| 0001 0003 | wait         | Awaits for another proccess to terminate |
| 0001 0004 | set_priority | Sets the scheduling priority of a task | 

## 0x02 - Virtual Memory
| opcode | name | description |
|--------|------|-------------|
| 0002 0000  | map     | Manually allocates and/or maps a page-based memory range |
| 0002 0001  | unmap   | Manually deallocates and unmaps a page-based memory range |
| 0002 0002  | query   | Returns information about a memory address |
| 0002 0003  | protect | Change page protection flags |

## 0x03 - Multitaking & syncronization
| opcode | name | description |
|--------|------|-------------|
| 0003 0000 | branch      | Create a new paralel task to run in the current process context |
| 0003 0001 | async_ret   | Returns from the current task |
| 0003 0002 | await       | Awaits for another task to asyncronously return |
| 0003 0003 | futex_await | |
| 0003 0004 | futex_awake | |
| 0003 0005 | yield       | Gives up the schedue to another task |
| 0003 0006 | sleep       | Makes the task awaits |

## 0x04 - Inter-Process Communication
| opcode | name | description |
|--------|------|-------------|
| 0004 0000 | signal_send     | Sends a signal to another proccess |
| 0004 0001 | signal_await    | Awaits for a specific signal to be sent |
| 0004 0002 | signal_handle   | Defines a handle for signals |
| 0004 0100 | mailbox_create  | Creates a mailbox |
| 0004 0101 | mailbox_destroy | Destroys a mailbox |
| 0004 0102 | mail_send       | Sends a message to another mailbox |
| 0004 0103 | mail_receive    | Pools a message from the mailbox |
| 0004 0200 | pipe_create     | Creates a stream pipe |
| 0004 0201 | pipe_destroy    | Destroys a stream pipe |
| 0004 0202 | pipe_write      | Write bytes into the pipe |
| 0004 0203 | pipe_read       | Read bytes outo the pipe |

## 0x05 - Files and Directories
| opcode | name | description |
|--------|------|-------------|
| 0005 0000 | new        | Creates a new file system entry |
| 0005 0001 | open       | Opens a new fs descriptor |
| 0005 0002 | close      | Closes a opened fs descriptor |
| 0005 0003 | read       | Reads a fs descriptor |
| 0005 0004 | write      | Writes to a fs descriptor |
| 0005 0005 | seek       | Redefines the current descriptor's offset |
| 0005 0006 | info       | Returns status information about the descriptor |
| 0005 0007 | path_info  | Returns status information about the path |

## 0x06 - I/O Devices
| opcode | name | description |
|--------|------|-------------|
| 0006 0000 | query    | Returns information about a specific device |
| 0006 0001 | open     | Opens a new device descriptor |
| 0006 0002 | close    | Closes a device descriptor |
| 0006 0003 | operate  | Sends a opcode to the device |

## 0x07 - Clock & Timers
| opcode | name | description |
|--------|------|-------------|
| 0007 0000 | get_time     | Returns the current timestamp |
| 0007 0001 | get_date     | Returns the current date |
| 0007 0002 | get_epoch    | Returns the epoch being used |
| 0007 0003 | get_ticks    | Returns the ticks counted since boot |
| 0007 0004 | timer_create | Creates a precision timer |
| 0007 0005 | timer_start  | Starts a precision timer |
| 0007 0006 | timer_reset  | Resets a precision timer |
| 0007 0007 | timer_query  | Gets the remaining timer of a precision timer |
| 0007 0008 | timer_cancel | Destroys an already created timer |

## 0x08 - System Information
| opcode | name | description |
|--------|------|-------------|
| 0008 0000 | query_kernel | Gets kernel information |
| 0008 0001 | query_user   | Gets user's information |
| 0008 0001 | query_cpu    | Gets CPU information |
| 0008 0002 | query_memory | Gets virtual memory information |


## 0x09 - Security & Permissions

## 0x0A - Debug
