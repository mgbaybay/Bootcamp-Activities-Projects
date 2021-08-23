# Enrollment Schema and EERD

Enrollment System for Elementary and High School Students

### Schema

```
-- MySQL Workbench Forward Engineering

SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0;
SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0;
SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION';

-- -----------------------------------------------------
-- Schema student_enrollment
-- -----------------------------------------------------

-- -----------------------------------------------------
-- Schema student_enrollment
-- -----------------------------------------------------
CREATE SCHEMA IF NOT EXISTS `student_enrollment` DEFAULT CHARACTER SET utf8 ;
USE `student_enrollment` ;

-- -----------------------------------------------------
-- Table `student_enrollment`.`student_information`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `student_enrollment`.`student_information` (
  `student_id` INT NOT NULL AUTO_INCREMENT,
  `first_name` VARCHAR(50) NOT NULL,
  `last_name` VARCHAR(50) NOT NULL,
  `email` VARCHAR(50) NOT NULL,
  `contact_number` VARCHAR(20) NOT NULL,
  `address` VARCHAR(200) NOT NULL,
  `date_created` TIMESTAMP NOT NULL,
  `date_modified` TIMESTAMP NOT NULL,
  PRIMARY KEY (`student_id`))
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `student_enrollment`.`subject_details`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `student_enrollment`.`subject_details` (
  `student_subject_id` INT NOT NULL AUTO_INCREMENT,
  `subject_name` VARCHAR(50) NOT NULL,
  `date_created` TIMESTAMP NULL,
  `date_modified` TIMESTAMP NULL,
  PRIMARY KEY (`student_subject_id`))
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `student_enrollment`.`instructor_information`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `student_enrollment`.`instructor_information` (
  `instructor_id` INT NOT NULL AUTO_INCREMENT,
  `first_name` VARCHAR(50) NOT NULL,
  `last_name` VARCHAR(50) NOT NULL,
  `email` VARCHAR(50) NOT NULL,
  `contact_number` VARCHAR(20) NOT NULL,
  `date_created` TIMESTAMP NOT NULL,
  `date_modified` TIMESTAMP NOT NULL,
  PRIMARY KEY (`instructor_id`))
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `student_enrollment`.`year_level`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `student_enrollment`.`year_level` (
  `yearlevel_id` INT NOT NULL AUTO_INCREMENT,
  `yearlevel_name` VARCHAR(50) NOT NULL,
  `date_created` TIMESTAMP NOT NULL,
  `date_modified` TIMESTAMP NOT NULL,
  PRIMARY KEY (`yearlevel_id`))
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `student_enrollment`.`school_year`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `student_enrollment`.`school_year` (
  `schoolyear_id` INT NOT NULL,
  `schoolyear_start` DATE NOT NULL,
  `schoolyear_end` DATE NOT NULL,
  `date_created` TIMESTAMP NOT NULL,
  `date_modified` TIMESTAMP NOT NULL,
  PRIMARY KEY (`schoolyear_id`))
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `student_enrollment`.`class_schedule`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `student_enrollment`.`class_schedule` (
  `class_id` INT NOT NULL AUTO_INCREMENT,
  `student_subject_id` INT NOT NULL,
  `instructor_id` INT NOT NULL,
  `yearlevel_id` INT NOT NULL,
  `room_number` VARCHAR(20) NOT NULL,
  `class_start_time` TIME NOT NULL,
  `class_end_time` TIME NOT NULL,
  `schoolyear_id` INT NOT NULL,
  `date_created` TIMESTAMP NOT NULL,
  `date_modified` TIMESTAMP NOT NULL,
  PRIMARY KEY (`class_id`),
  INDEX `FK_subject_id_idx` (`student_subject_id` ASC) VISIBLE,
  INDEX `FK_instructor_id_idx` (`instructor_id` ASC) VISIBLE,
  INDEX `FK_yearlevel_id_idx` (`yearlevel_id` ASC) VISIBLE,
  INDEX `FK_schoolyear_id_idx` (`schoolyear_id` ASC) VISIBLE,
  CONSTRAINT `FK_student_subject_id`
    FOREIGN KEY (`student_subject_id`)
    REFERENCES `student_enrollment`.`subject_details` (`student_subject_id`)
    ON DELETE RESTRICT
    ON UPDATE CASCADE,
  CONSTRAINT `FK_instructor_id`
    FOREIGN KEY (`instructor_id`)
    REFERENCES `student_enrollment`.`instructor_information` (`instructor_id`)
    ON DELETE RESTRICT
    ON UPDATE CASCADE,
  CONSTRAINT `FK_yearlevel_id`
    FOREIGN KEY (`yearlevel_id`)
    REFERENCES `student_enrollment`.`year_level` (`yearlevel_id`)
    ON DELETE RESTRICT
    ON UPDATE CASCADE,
  CONSTRAINT `FK_schoolyear_id`
    FOREIGN KEY (`schoolyear_id`)
    REFERENCES `student_enrollment`.`school_year` (`schoolyear_id`)
    ON DELETE RESTRICT
    ON UPDATE CASCADE)
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `student_enrollment`.`payment_details`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `student_enrollment`.`payment_details` (
  `payment_id` INT NOT NULL,
  `date` TIMESTAMP NOT NULL,
  PRIMARY KEY (`payment_id`))
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `student_enrollment`.`registration_details`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `student_enrollment`.`registration_details` (
  `registration_id` INT NOT NULL,
  `student_id` INT NOT NULL,
  `class_id` INT NOT NULL,
  `payment_id` INT NOT NULL,
  `date_created` TIMESTAMP NOT NULL,
  `date_modified` TIMESTAMP NOT NULL,
  PRIMARY KEY (`registration_id`),
  INDEX `FK_class_id_idx` (`class_id` ASC) VISIBLE,
  INDEX `FK_payment_id_idx` (`payment_id` ASC) VISIBLE,
  INDEX `FK_student_id_idx` (`student_id` ASC) VISIBLE,
  CONSTRAINT `FK_class_id`
    FOREIGN KEY (`class_id`)
    REFERENCES `student_enrollment`.`class_schedule` (`class_id`)
    ON DELETE RESTRICT
    ON UPDATE CASCADE,
  CONSTRAINT `FK_payment_id`
    FOREIGN KEY (`payment_id`)
    REFERENCES `student_enrollment`.`payment_details` (`payment_id`)
    ON DELETE RESTRICT
    ON UPDATE CASCADE,
  CONSTRAINT `FK_student_id`
    FOREIGN KEY (`student_id`)
    REFERENCES `student_enrollment`.`student_information` (`student_id`)
    ON DELETE RESTRICT
    ON UPDATE CASCADE)
ENGINE = InnoDB;


SET SQL_MODE=@OLD_SQL_MODE;
SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS;
SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS;

```

***************
### EERD Diagram
<img src='https://github.com/mgbaybay/mgbaybay-kodego/blob/main/MySQL%20Enrollment%20Schema%20and%20EERD/mgbaybay_enrollment_eerd.png'>
