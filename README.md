# ContactMaster

Designed and implemented demo application for maintaining
contact information. 

Used below technology to implemt the same:
    Asp.net, MVC5, Entity Framwork5(using database first approach

Visual studio 2017 and SQL server 2017 is used

Implemented functionality:
- List contacts
- Add a contact
- Edit contact
- Delete/Inactivate a contact

Contact model fields is:
- FirstName
- LastName
- EmailId
- PhoneNumber
- Status

Code Details:
	- Attached Zip file which contains complete code, including MVC controller, Web API controller, views etc.
	- As packages folder size is more than 30mb so divide it into two seprate Zip file Package1 & Package2.
	- Below I have attached DB script.
	

Database details:
  Created "ContactMaster" database with table named as "CustomerDtl":
  Below I have attached ContactMaster DB schema script:
  
  USE [master]
GO
/****** Object:  Database [ContactMaster]    Script Date: 05-04-2020 13:41:21 ******/
CREATE DATABASE [ContactMaster]
 CONTAINMENT = NONE
 ON  PRIMARY 
( NAME = N'ContactMaster', FILENAME = N'C:\Program Files\Microsoft SQL Server\MSSQL15.TPMSSQLSERVER\MSSQL\DATA\ContactMaster.mdf' , SIZE = 8192KB , MAXSIZE = UNLIMITED, FILEGROWTH = 65536KB )
 LOG ON 
( NAME = N'ContactMaster_log', FILENAME = N'C:\Program Files\Microsoft SQL Server\MSSQL15.TPMSSQLSERVER\MSSQL\DATA\ContactMaster_log.ldf' , SIZE = 8192KB , MAXSIZE = 2048GB , FILEGROWTH = 65536KB )
 WITH CATALOG_COLLATION = DATABASE_DEFAULT
GO
ALTER DATABASE [ContactMaster] SET COMPATIBILITY_LEVEL = 150
GO
IF (1 = FULLTEXTSERVICEPROPERTY('IsFullTextInstalled'))
begin
EXEC [ContactMaster].[dbo].[sp_fulltext_database] @action = 'enable'
end
GO
ALTER DATABASE [ContactMaster] SET ANSI_NULL_DEFAULT OFF 
GO
ALTER DATABASE [ContactMaster] SET ANSI_NULLS OFF 
GO
ALTER DATABASE [ContactMaster] SET ANSI_PADDING OFF 
GO
ALTER DATABASE [ContactMaster] SET ANSI_WARNINGS OFF 
GO
ALTER DATABASE [ContactMaster] SET ARITHABORT OFF 
GO
ALTER DATABASE [ContactMaster] SET AUTO_CLOSE OFF 
GO
ALTER DATABASE [ContactMaster] SET AUTO_SHRINK OFF 
GO
ALTER DATABASE [ContactMaster] SET AUTO_UPDATE_STATISTICS ON 
GO
ALTER DATABASE [ContactMaster] SET CURSOR_CLOSE_ON_COMMIT OFF 
GO
ALTER DATABASE [ContactMaster] SET CURSOR_DEFAULT  GLOBAL 
GO
ALTER DATABASE [ContactMaster] SET CONCAT_NULL_YIELDS_NULL OFF 
GO
ALTER DATABASE [ContactMaster] SET NUMERIC_ROUNDABORT OFF 
GO
ALTER DATABASE [ContactMaster] SET QUOTED_IDENTIFIER OFF 
GO
ALTER DATABASE [ContactMaster] SET RECURSIVE_TRIGGERS OFF 
GO
ALTER DATABASE [ContactMaster] SET  DISABLE_BROKER 
GO
ALTER DATABASE [ContactMaster] SET AUTO_UPDATE_STATISTICS_ASYNC OFF 
GO
ALTER DATABASE [ContactMaster] SET DATE_CORRELATION_OPTIMIZATION OFF 
GO
ALTER DATABASE [ContactMaster] SET TRUSTWORTHY OFF 
GO
ALTER DATABASE [ContactMaster] SET ALLOW_SNAPSHOT_ISOLATION OFF 
GO
ALTER DATABASE [ContactMaster] SET PARAMETERIZATION SIMPLE 
GO
ALTER DATABASE [ContactMaster] SET READ_COMMITTED_SNAPSHOT OFF 
GO
ALTER DATABASE [ContactMaster] SET HONOR_BROKER_PRIORITY OFF 
GO
ALTER DATABASE [ContactMaster] SET RECOVERY SIMPLE 
GO
ALTER DATABASE [ContactMaster] SET  MULTI_USER 
GO
ALTER DATABASE [ContactMaster] SET PAGE_VERIFY CHECKSUM  
GO
ALTER DATABASE [ContactMaster] SET DB_CHAINING OFF 
GO
ALTER DATABASE [ContactMaster] SET FILESTREAM( NON_TRANSACTED_ACCESS = OFF ) 
GO
ALTER DATABASE [ContactMaster] SET TARGET_RECOVERY_TIME = 60 SECONDS 
GO
ALTER DATABASE [ContactMaster] SET DELAYED_DURABILITY = DISABLED 
GO
ALTER DATABASE [ContactMaster] SET QUERY_STORE = OFF
GO
USE [ContactMaster]
GO
/****** Object:  Table [dbo].[CustomerDtl]    Script Date: 05-04-2020 13:41:21 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[CustomerDtl](
	[ContactId] [int] IDENTITY(1,1) NOT NULL,
	[FirstName] [nvarchar](50) NULL,
	[LastName] [nvarchar](50) NULL,
	[EmailId] [nvarchar](50) NULL,
	[PhoneNumber] [nchar](10) NULL,
	[Status] [int] NULL,
 CONSTRAINT [PK_CustomerDtl] PRIMARY KEY CLUSTERED 
(
	[ContactId] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
USE [master]
GO
ALTER DATABASE [ContactMaster] SET  READ_WRITE 
GO

